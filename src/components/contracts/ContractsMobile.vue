<template>
  <container fluid class="p-0">
    <h4>Contracts</h4>
    <card v-for="item in data" class="mt-2">
      <card-body>
        <card-text>
          <row class="m-0">
            <div class="rounded-circle grey lighten-2 text-center float-left">
              <fa icon="file-text-o"/>
            </div>
            <div class="float-left pl-2">
              <h5 class="m-0">{{ item.name }}</h5>
              <p class="m-0">Sent By: <span class="blue-grey-text">{{ item.sentBy }}</span></p>
              <p class="m-0">Sent At: <span class="blue-grey-text">{{ item.date }}</span></p>
              <p class="m-0">Status: 
                <span v-if="item.completed" class="light-green-text">Complete</span>
                <span v-else class="red-text">Open</span>
              </p>
            </div>
          </row>
          <btn v-if="!item.completed" color="light-green" class="ml-5" size="sm">COMPLETE</btn>
        </card-text>
      </card-body>
    </card>
  </container>
</template>

<script>
import { Container, Row, Card, CardTitle, CardBody, CardText, Fa, Btn } from 'mdbvue';

export default {
  name: 'Contracts',
  components: {
    Container,
    Row,
    Card,
    CardTitle,
    CardBody,
    CardText,
    Fa,
    Btn
  },
  props: {
    data: {
      type: Array,
      default: []
    }
  }
};
</script>

<style lang="scss" scoped>
.card {
  .rounded-circle {
    width: 30px;
    height: 30px;
    padding-top: 5px;
    .fa {
      color: #f15d2e;
    }
  }
}
</style>
