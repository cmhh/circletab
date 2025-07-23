<script setup>
import CircleTab from './components/CircleTab.vue'
</script>
  
<template>
  <p>Bacon ipsum dolor amet buffalo ham leberkas pork loin filet mignon jowl jerky salami turducken ribeye boudin kevin pastrami. Ground round jowl strip steak chicken pork belly, turducken beef ribs tri-tip boudin cupim. Pancetta tenderloin drumstick, alcatra short ribs pork shankle meatloaf pork chop venison salami brisket fatback bresaola. Buffalo pork loin ball tip flank ham, alcatra filet mignon brisket ribeye. Turkey fatback drumstick sausage, ball tip chicken meatball capicola strip steak prosciutto flank alcatra beef ribs sirloin. T-bone shoulder sirloin shank leberkas short ribs. Bresaola leberkas corned beef meatball.</p>

  <p>Pig shank meatloaf pork chop jerky flank kielbasa, spare ribs ball tip bresaola shoulder. Pancetta pastrami alcatra cupim ground round. Pork sirloin doner pig. Shankle corned beef ball tip capicola, pork loin turkey landjaeger biltong cupim. Doner tenderloin drumstick leberkas sausage ground round cupim t-bone andouille meatball. Chicken short ribs cow leberkas filet mignon rump pork loin shank shankle sirloin tri-tip tail pig bacon. Shankle jerky short ribs tongue rump pig strip steak beef shank leberkas salami.</p>
  
  <p>Bacon ipsum dolor amet buffalo ham leberkas pork loin filet mignon jowl jerky salami turducken ribeye boudin kevin pastrami. Ground round jowl strip steak chicken pork belly, turducken beef ribs tri-tip boudin cupim. Pancetta tenderloin drumstick, alcatra short ribs pork shankle meatloaf pork chop venison salami brisket fatback bresaola. Buffalo pork loin ball tip flank ham, alcatra filet mignon brisket ribeye. Turkey fatback drumstick sausage, ball tip chicken meatball capicola strip steak prosciutto flank alcatra beef ribs sirloin. T-bone shoulder sirloin shank leberkas short ribs. Bresaola leberkas corned beef meatball.</p>
  
  <p>Bacon ipsum dolor amet buffalo ham leberkas pork loin filet mignon jowl jerky salami turducken ribeye boudin kevin pastrami. Ground round jowl strip steak chicken pork belly, turducken beef ribs tri-tip boudin cupim. Pancetta tenderloin drumstick, alcatra short ribs pork shankle meatloaf pork chop venison salami brisket fatback bresaola. Buffalo pork loin ball tip flank ham, alcatra filet mignon brisket ribeye. Turkey fatback drumstick sausage, ball tip chicken meatball capicola strip steak prosciutto flank alcatra beef ribs sirloin. T-bone shoulder sirloin shank leberkas short ribs. Bresaola leberkas corned beef meatball.</p>

  <CircleTab 
    :data="[
      {outcome: 'Foo', values: {A: 1.0, B: 0.2, C: 0.3}},
      {outcome: 'Bar', values: {A: 0.4, B: 0.3, C: 0.1}},
      {outcome: 'Baz', values: {A: 0.2, B: 0.8, C: 0.2}}
    ]"
    :maxVal="1"
  />

  <p>Bacon ipsum dolor amet buffalo ham leberkas pork loin filet mignon jowl jerky salami turducken ribeye boudin kevin pastrami. Ground round jowl strip steak chicken pork belly, turducken beef ribs tri-tip boudin cupim. Pancetta tenderloin drumstick, alcatra short ribs pork shankle meatloaf pork chop venison salami brisket fatback bresaola. Buffalo pork loin ball tip flank ham, alcatra filet mignon brisket ribeye. Turkey fatback drumstick sausage, ball tip chicken meatball capicola strip steak prosciutto flank alcatra beef ribs sirloin. T-bone shoulder sirloin shank leberkas short ribs. Bresaola leberkas corned beef meatball.</p>

  <p>Pig shank meatloaf pork chop jerky flank kielbasa, spare ribs ball tip bresaola shoulder. Pancetta pastrami alcatra cupim ground round. Pork sirloin doner pig. Shankle corned beef ball tip capicola, pork loin turkey landjaeger biltong cupim. Doner tenderloin drumstick leberkas sausage ground round cupim t-bone andouille meatball. Chicken short ribs cow leberkas filet mignon rump pork loin shank shankle sirloin tri-tip tail pig bacon. Shankle jerky short ribs tongue rump pig strip steak beef shank leberkas salami.</p>
  
  <p>Bacon ipsum dolor amet buffalo ham leberkas pork loin filet mignon jowl jerky salami turducken ribeye boudin kevin pastrami. Ground round jowl strip steak chicken pork belly, turducken beef ribs tri-tip boudin cupim. Pancetta tenderloin drumstick, alcatra short ribs pork shankle meatloaf pork chop venison salami brisket fatback bresaola. Buffalo pork loin ball tip flank ham, alcatra filet mignon brisket ribeye. Turkey fatback drumstick sausage, ball tip chicken meatball capicola strip steak prosciutto flank alcatra beef ribs sirloin. T-bone shoulder sirloin shank leberkas short ribs. Bresaola leberkas corned beef meatball.</p>
  
  <p>Bacon ipsum dolor amet buffalo ham leberkas pork loin filet mignon jowl jerky salami turducken ribeye boudin kevin pastrami. Ground round jowl strip steak chicken pork belly, turducken beef ribs tri-tip boudin cupim. Pancetta tenderloin drumstick, alcatra short ribs pork shankle meatloaf pork chop venison salami brisket fatback bresaola. Buffalo pork loin ball tip flank ham, alcatra filet mignon brisket ribeye. Turkey fatback drumstick sausage, ball tip chicken meatball capicola strip steak prosciutto flank alcatra beef ribs sirloin. T-bone shoulder sirloin shank leberkas short ribs. Bresaola leberkas corned beef meatball.</p>
</template>

<style scoped>
p {
  min-width: 600px;
}
</style>
