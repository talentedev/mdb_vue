<template>
  <container class="mt-5">
    <h2 class="title mb-5"><strong>Checkboxes</strong></h2>

    <h4 class="mt-5 mb-3">Basic examples</h4>
    <MdInput type="checkbox" id="checkbox1" label="Default checkbox" />
    <MdInput type="checkbox" id="checkbox2" label="Filled-in checkbox" filled/>

    <h4 class="mt-5 mb-3">Disabled checkboxes</h4>
    <MdInput type="checkbox" id="checkbox3" label="Default checkbox" disabled/>
    <MdInput type="checkbox" id="checkbox4" label="Filled-in checkbox" filled disabled/>

    <h4 class="mt-5 mb-3">Inline checkboxes</h4>
    <form-inline>
      <MdInput type="checkbox" id="checkbox5" label="Default checkobox" />
      <MdInput type="checkbox" id="checkbox6" label="Filled-in checkobox" filled/>
      <MdInput type="checkbox" id="checkbox7" label="Default checkobox" />
    </form-inline>

    <hr class="my-5" />
    <h2 class="title mb-5"><strong>Radio buttons</strong></h2>

    <h4 class="mt-5 mb-3">Basic examples</h4>
    <MdInput type="radio"
             @click.native="toggleRadio1"
             :checked="radio1 === 1"
             label="Option 1"></MdInput>
    <MdInput type="radio"
             @click.native="toggleRadio2"
             :checked="radio1 === 2"
             label="Option 2"></MdInput>
    <MdInput type="radio"
             @click.native="toggleRadio3"
             :checked="radio1 === 3"
             label="Option 3"></MdInput>

    <h4 class="mt-5 mb-3">Radio buttons with gap</h4>
    <MdInput type="radio"
             gap
             :checked="radio2 === 1"
             @click.native="toggleRadio4"
             label="Option 1"></MdInput>
    <MdInput type="radio"
             gap
             @click.native="toggleRadio5"
             :checked="radio2 === 2"
             label="Option 2"></MdInput>
    <MdInput type="radio"
             gap
             @click.native="toggleRadio6"
             :checked="radio2 === 3"
             label="Option 3"></MdInput>

    <h4 class="mt-5 mb-3">Inline radio buttons</h4>
    <form-inline>
      <MdInput type="radio"
               :checked="radio3 === 1"
               @click.native="toggleRadio7"
               label="Option 1"></MdInput>
      <MdInput type="radio"
               @click.native="toggleRadio8"
               :checked="radio3 === 2"
               label="Option 2"></MdInput>
      <MdInput type="radio"
               @click.native="toggleRadio9"
               :checked="radio3 === 3"
               label="Option 3"></MdInput>
    </form-inline>

    <hr class="my-5" />
    <h2 class="title mb-5"><strong>Switch</strong></h2>
    <md-switch />
    <h4 class="mt-5 mb-3">Disabled</h4>
    <md-switch disabled />

    <hr class="my-5" />
    <h2 class="title mb-5"><strong>File input</strong></h2>
    <h4 class="mt-5 mb-3">Basic example</h4>
    <file-input />
    <h4 class="mt-5 mb-3">Multiple files</h4>
    <file-input multiple btnColor="teal"></file-input>

    <hr class="my-5" />
    <h2 class="title mb-5"><strong>Range</strong></h2>
    <range-input :min="0" :max="100" :value="50"></range-input>
    <div style="height: 60px;"></div>

  </container>
</template>

<script>
import { Container, MdInput, FormInline, MdSwitch, FileInput, RangeInput } from 'mdbvue';

export default {
  name: 'InputsProPage',
  components: {
    Container,
    MdInput,
    FormInline,
    MdSwitch,
    FileInput,
    RangeInput
  },
  data() {
    return {
      radio1: 0,
      radio2: 0,
      radio3: 0
    };
  },
  methods: {
    toggleRadio1() {
      this.radio1 = 1;
    },
    toggleRadio2() {
      this.radio1 = 2;
    },
    toggleRadio3() {
      this.radio1 = 3;
    },
    toggleRadio4() {
      this.radio2 = 1;
    },
    toggleRadio5() {
      this.radio2 = 2;
    },
    toggleRadio6() {
      this.radio2 = 3;
    },
    toggleRadio7() {
      this.radio3 = 1;
    },
    toggleRadio8() {
      this.radio3 = 2;
    },
    toggleRadio9() {
      this.radio3 = 3;
    },
  }
};

</script>

<style>
</style>
