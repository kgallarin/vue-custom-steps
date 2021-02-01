<template>
  <step-wrapper 
    finishButtonText="Finish"
    :next-button-text="['Next']"
    class="wrapper"
  >
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
    
    <steps-tab
      title="Hello I am Step 3"
      :before-change="() => validateStep('sampleStepTwo')"
    >
      <page-three 
        @on-validated="onStepValidated"
        ref="sampleStepTwo" 
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
      console.log(this.$refs[ref].validate())
      return this.$refs[ref].validate()
    },
    onStepValidated(validated) {
      return validated
    }
  }
}
</script>