<template>
  <step-wrapper 
    finish-button-text="Finish"
    :next-button-text="['Next']"
    class="wrapper"
  >
  
    <!-- page one -->
    <steps-tab
      title="Hello I am Step 1"
      :before-change="() => validateStep('sampleStepOne')"
    >
      <page-one  
        @on-validated="onStepValidated"
        ref="sampleStepOne" 
      />
    </steps-tab>
    
    <!-- page two -->
    <steps-tab
      title="Hello I am Step 2"
      :before-change="() => validateStep('sampleStepTwo')"
    >
      <page-two 
        @on-validated="onStepValidated"
        ref="sampleStepTwo" 
      />
    </steps-tab>
    
    <!-- page three -->
    <steps-tab
      title="Hello I am Step 3"
      :before-change="() => validateStep('sampleStepThree')"
    >
      <page-three 
        @on-validated="onStepComplete"
        ref="sampleStepThree" 
      />
    </steps-tab>
    
  </step-wrapper>
</template>
<script>
import StepWrapper from "./StepsWizard/StepWrapper"
import StepsTab from "./StepsWizard/StepTab"

import PageOne from "./StepPages/page-one"
import PageTwo from "./StepPages/page-two"
import PageThree from "./StepPages/page-three"

export default {
  name: 'SteppingSample1',
  components: {
    StepWrapper,
    StepsTab,
    PageOne,
    PageTwo,
    PageThree
  },
  methods: {
    validateStep(ref) {
      // console.log('vasd')
      return this.$refs[ref].validate()
    },
    onStepValidated(validated) {
      // console.log(validated)
      return validated
    },
    onStepComplete() {
      alert('Step completed!')
    }
  }
}
</script>