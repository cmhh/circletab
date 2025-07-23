<script setup>
import {computed, onMounted, ref} from 'vue'

const props = defineProps({
  data: {
    type: Object,
    required: true
  },
  maxVal: {
    type: Number,
    required: false
  },
  fillColor: {
    type: String,
    required: false,
    default: "rgba(59, 130, 246, .5)"
  },
  strokeWidth: {
    type: Number,
    required: false,
    default: 2
  },
  strokeColor: {
    type: String,
    required: false,
    default: "#666"
  }
})

const tabContainer = ref(null)

const circle = (v) => {
  console.log(`v: ${v}, mx.value: ${mx.value}, r: ${v / 2 / mx.value * 100}`)
  return `
  <svg viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
    <circle
      cx="50"
      cy="50"
      r="${v / 2 / mx.value * 100}"
      stroke="${props.strokeColor}"
      stroke-width="${props.strokeWidth}"
      fill="${props.fillColor}"
    />
  </svg>
  `
}

const mn = computed(() => {
  const rowmin = props.data.map((x) => Math.min(...Object.values(x['values'])))
  return Math.min(...rowmin)
})

const mx = computed(() => {
  if (props.maxVal) return props.maxVal
  const rowmax = props.data.map((x) => Math.max(...Object.values(x['values'])))
  return Math.max(...rowmax)
})

const outcomes = computed(() => {
  return props.data.map((x) => x['outcome'])
})

const cats = computed(() => {
  return Object.keys(props.data[0]['values'])
})

const hdr = computed(() => {
  return `<th></th>` + cats.value.map((x) => `<th>${x}</th>`).join('')
})

const rows = computed(() => {
  return props.data.map((x) => {
    const outcome = `<td>${x['outcome']}</td>`
    const values = cats.value.map((y) => {
      const v = x['values'][y]
      const s = circle(v)
      return `
        <td class=data>
          <div class=circ>${s}</div>
          <div class=value><p>${v}</p></div>
          <div class="tooltip hidden">${v}</div>
        </td>
      `
    }).join('')
    return `<tr>${outcome}${values}</tr>`
  }).join('')
})

const tbody = computed(() => {
  return `
  <thead>
    ${hdr.value}
  </thead>
  <tbody>
    ${rows.value}
  </tbody>
  `
})

onMounted(() => {
  const tbl = tabContainer.value
  const dat = tbl.querySelectorAll("td.data")
  for (var i = 0; i < dat.length; i++) {
    const circ = dat[i].querySelector("div.circ > svg > circle")
    const ttip = dat[i].querySelector("div.tooltip")

    circ.addEventListener('mouseover', (e) => {
      ttip.classList.remove("hidden")
    })

    circ.addEventListener('mouseout', (e) => {
      ttip.classList.add("hidden")
    })

    circ.addEventListener('mousemove', (e) => {
      e.preventDefault()
      ttip.style.left = (e.offsetX - 5) + "px"
      ttip.style.top = (e.offsetY - ttip.offsetHeight - 5) + "px"
    })
  }
})
</script>

<template>
  <div>
    <table ref="tabContainer" v-html="tbody" class="circle-tab"></table>
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Lato');

table.circle-tab {
  font-family: proxima-nova, "Lato", Arial, Helvetica, sans-serif;
  border-collapse: collapse;
}

table.circle-tab th, table.circle-tab td {
  border: none;
  vertical-align: middle!important;
}

table.circle-tab > thead {
  border-bottom: 1px solid black!important;
}

table.circle-tab > tbody > tr > td.data {
  position: relative;
  width: 100px;
  height: 100px;
}

table.circle-tab > tbody > tr > td.data > div.circ {
  position: absolute;
  display: grid;
  place-items: center;
  width: 100%;
  height: 100%;
  top: 0; left: 0;
}

table.circle-tab > tbody > tr > td.data > div.circ > svg {
  /* margin: auto auto; */
}

table.circle-tab > tbody > tr > td.data > div.value {
  display: block;
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0; left: 0;
  text-align: center;
  vertical-align: middle!important;
  display: none;
}

table.circle-tab > tbody > tr > td.data > div.value > p {
  color: white;
  text-shadow: -1px -1px 0 #000, 1px -1px 0 #000, -1px 1px 0 #000, 1px 1px 0 #000;
  font-weight: bold;
}

table.circle-tab > tbody > tr > td.data > div.tooltip {
  position: absolute;
  top: 0; left: 0;
  border: 1px solid black;
  border-radius: 5px;
  padding: 5px;
  background-color: #333;
  color: #FFFFFF;
  text-align: center;
  width: fit-content;
}

table.circle-tab > tbody > tr > td.data > div.tooltip.hidden {
  display: none;
}

table.circle-tab > tbody > tr > td.data > div.tooltip::after {
  content: " ";
  position: absolute;
  top: 100%; /* At the bottom of the tooltip */
  left: 10%;
  margin-left: 0;
  border-width: 5px;
  border-style: solid;
  border-color: #333 transparent transparent transparent;
}
</style>
