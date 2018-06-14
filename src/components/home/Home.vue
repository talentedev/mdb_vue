<template>
  <container fluid>
    <row>
      <column xl="8">
        <div class="card-deck mb-2">
          <card>
            <card-body>
              <card-title>Track your days</card-title>
              <card-text class="p-3">
                <row>
                  <column class="deep-orange lighten-1 p-3">
                    <div class="fit-content">
                      <img src="../../assets/img/circle-plus.png" class="float-left">
                      <div class="float-left pl-3">
                        <h5 class="m-0 white-text">Today</h5>
                        <p class="m-0 white-text"><small>May 11, 2018</small></p>
                      </div>
                    </div>
                  </column>
                </row>
                <row class="mt-3">
                  <column class="p-0 pr-1">
                    <div class="border border-success p-2">
                      <div class="fit-content">
                        <p class="m-0 red-text">Yesterday</p>
                        <p class="m-0"><small>May 10, 2018</small></p>
                      </div>
                    </div>
                  </column>
                  <column  class=" p-0 pl-1">
                    <div class="border border-success p-2">
                      <div class="fit-content">
                        <p class="m-0 lime-text">Wednesday</p>
                        <p class="m-0"><small>May 10, 2018</small></p>
                      </div>
                    </div>
                  </column>
                </row>
              </card-text>
              <a class="link-text"><h7>SEE MORE DAYS <fa icon="chevron-right" class="pl-1" /></h7></a>
            </card-body>
          </card>
          <card>
            <card-body>
              <card-title>
                <row>
                  <span>Progress</span>
                  <select-wrapper class="ml-auto">
                    <select-input @click.native="openSelect(0)" :text="text[0]"></select-input>
                    <transition @before-enter="beforeEnter" @enter="enter" @after-enter="afterEnter" @before-leave="beforeLeave">
                      <select-options v-show="active[0]" class="collapse-item">
                        <select-option disabled>Choose your option</select-option>
                        <select-option @click.native="chooseOption" value="Option 1">Last 7 days</select-option>
                        <select-option @click.native="chooseOption" value="Option 2">Last 30 days</select-option>
                      </select-options>
                    </transition>
                  </select-wrapper>
                </row>
              </card-title>
              <card-text class="float-none">
                <row>
                  <column col="6">
                    <div class="d-flex justify-content-center">
                      <mini-chart :value="diaryDays" color="#246e9a" diameter="130" strokeWidth="10">
                        {{diaryDays}}%
                      </mini-chart>
                    </div>
                    <div class="text-center pt-2">
                      <p class="m-0">Diary days</p>
                    </div>
                  </column>
                  <column col="6">
                    <div class="d-flex justify-content-center">
                      <mini-chart :value="uniteWeek" color="#82d929" diameter="130" strokeWidth="10">
                        {{uniteWeek}}%
                      </mini-chart>
                    </div>
                    <div class="text-center pt-2">
                      <p class="m-0">Unites this week</p>
                      <p><small>last week 12</small></p>
                    </div>
                  </column>
                </row>
              </card-text>
              <a class="link-text"><h7>SEE PROGRESS REPORT <fa icon="chevron-right" class="pl-1" /></h7></a>
            </card-body>
          </card>
        </div>
      </column>
      <column xl="4">
        <card>
          <card-body class="p-0">
            <card-title class="deep-orange lighten-1 p-3">
              <p class="white-text m-0">Important</p>
              <p class="white-text m-0"><small>These items need your attention...</small></p>
            </card-title>
            <card-text class="p-3">
              <div>
                <fa icon="star" class="blue-text"/>
                <span>Forms: 4 need completed</span>
                <a href="#" class="orange-text"><ins>Start now</ins></a>
              </div>
              <div class="mt-2">
                <fa icon="star" class="blue-text"/>
                <span>Contracts: 2 need excuted</span>
                <a href="#" class="orange-text"><ins>Start now</ins></a>
              </div>
            </card-text>
          </card-body>
        </card>
      </column>
    </row>
    <row class="mt-3">
      <column xl="8">
        <div class="card-deck">
          <card>
            <card-body>
              <card-title>
                <p class="m-0">New messages!</p>
                <p class="m-0 blue-grey-text"><small>You have (3) Unreaded Messages</small></p>
              </card-title>
              <card-text class="grey lighten-4 p-3">
                <row class="m-0">
                  <img src="../../assets/img/avatar.png" width="35" height="35" class="float-left">
                  <div class="float-left pl-2">
                    <p class="m-0">Jeff Magnusson</p>
                    <p class="m-0 blue-grey-text"><small>I think it's only important to have...</small></p>
                  </div>
                </row>
                <btn color="light-green ml-5" size="sm">READ NOW</btn>
              </card-text>
              <a class="link-text"><h7>ALL MESSAGES <fa icon="chevron-right" class="pl-1" /></h7></a>
            </card-body>
          </card>
          <card>
            <card-body>
              <card-title>Upcoming appointments</card-title>
              <card-text class="grey lighten-4 p-3">
                <p class="m-0 blue-grey-text"><small>Today 2:00 PM</small></p>
                <p class="m-0">Meet Dr.Jeff Magnusson (Founder of Alavida)</p>
                <btn color="light-green" size="sm">JOIN NOW</btn>
              </card-text>
              <a class="link-text"><h7>FULL SCHEDULE <fa icon="chevron-right" class="pl-1" /></h7></a>
            </card-body>
          </card>
        </div>
      </column>
    </row>
  </container>
</template>

<script>
import { Container, Row, Column, Card, CardHeader, CardBody, CardTitle, CardText, Fa, SelectWrapper, SelectInput, SelectOptions, SelectOption, Btn, MiniChart } from 'mdbvue';
export default {
  name: 'Home',
  components: {
    Container,
    Row,
    Column,
    Card,
    CardHeader,
    CardBody,
    CardTitle,
    CardText,
    Fa,
    SelectWrapper,
    SelectInput,
    SelectOptions,
    SelectOption,
    Btn,
    MiniChart
  },
  data() {
    return {
      value: {
        0: false
      },
      text: {
        0: ""
      },
      active: {
        0: false
      },
      activeSelect: false,
      elHeight: false,
      multiValues: [],
      multiTexts: [],
      diaryDays: 85,
      uniteWeek: 65
    };
  },
  methods: {
    openSelect(index) {
      for (let i = 0; i < Object.keys(this.active).length; i++) {
        if (index !== i) {
          this.active[i] = false;
        }
      }
      this.active[index] = true;
      this.activeSelect = index;
    },
    chooseOption(e) {
      // check if select is multiple
      if (e.target.dataset.multiple === 'true') {
        if (this.multiValues.includes(e.target.getAttribute('data-value'))) {
          let valueIndex = this.multiValues.indexOf(e.target.getAttribute('data-value'));
          this.multiValues.splice(valueIndex, 1);
          this.multiTexts.splice(valueIndex, 1);
          e.target.parentNode.classList.remove('active');
          e.target.parentNode.getElementsByTagName('input')[0].removeAttribute('checked');
          if (!this.multiValues.length) {
            this.multiValues = [];
            this.multiTexts = "";
          }
        } else {
          if (this.multiTexts === "") {
            this.multiValues = [];
            this.multiTexts = [];
          }
          this.multiValues.push(e.target.getAttribute('data-value'));
          this.multiTexts.push(e.target.parentNode.getElementsByClassName('filtrable')[0].textContent);
          e.target.parentNode.classList.add('active');
          e.target.parentNode.getElementsByTagName('input')[0].setAttribute('checked', true);
        }
        this.value[this.activeSelect] = this.multiValues;
        this.text[this.activeSelect] = this.multiTexts;
      // if not multiple
      } else {
        let activeOption = e.target.parentNode.parentNode.getElementsByClassName('active')[0];
        if (activeOption) {
          activeOption.classList.remove('active');
        }
        e.target.parentNode.classList.add('active');
        this.value[this.activeSelect] = e.target.getAttribute('data-value');
        this.text[this.activeSelect] = e.target.parentNode.getElementsByClassName('filtrable')[0].textContent;
      }
    },
    beforeEnter(el) {
      el.style.display = 'block';
      this.elHeight = el.scrollHeight;
    },
    enter(el) {
      el.style.display = 'block';
      el.style.opacity = 1;
      el.style.height = this.elHeight + 'px';
    },
    afterEnter(el) {
      el.style.overflowY = 'auto';
    },
    beforeLeave(el) {
      el.style.overflowY = 'hidden';
      el.style.opacity = 0;
      el.style.height = 0;
      this.remove = setTimeout(() => {
        el.style.display = 'none';
      }, 500);
    },
    allDropdownsClose(target) {
      // check if target is multiple select
      if (target) {
        if (target.dataset.multiple === 'true') {
          return;
        }
      }
      for (let i = 0; i < Object.keys(this.active).length; i++) {
        this.active[i] = false;
      }
    },
    onClick(e) {
      if (!e.target.classList.contains('select-dropdown')) {
        this.allDropdownsClose(e.target);
      }
    }
  },
  mounted() {
    document.addEventListener('click', this.onClick);
  },
  destroyed() {
    document.removeEventListener('click', this.onClick);
  }
};

</script>

<style lang="scss" scoped>
.card-title {
  font-size: 16px;
}
.link-text {
  font-size: 12px;
  color: #225cd9 !important;
}
.fit-content {
  width: fit-content;
  margin: auto;
}
.select-wrapper {
  width: 110px;
  display: inline-block;
  input {
    height: 25px;
    font-size: 13px;
  }
}
</style>

<style lang="scss">
.select-wrapper {
  span.caret {
    top: 5px;
  }
}
</style>
