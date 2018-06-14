<template>
  <container fluid>
    <div v-if="isMobile">
      <contracts-mobile :data="gridData"/>
    </div>
    <div v-else>
      <card>
        <card-body>
          <card-title>Contracts</card-title>
          <card-text>
            <tbl hover responsive-lg>
              <tbl-head>
                <tr>
                  <th></th>
                  <th>Name</th>
                  <th>Sent by</th>
                  <th>Date</th>
                  <th>Status</th>
                  <th>Action</th>
                </tr>
              </tbl-head>
              <tbl-body>
                <tr v-for="contract of contracts">
                  <td class="tbl-index">
                    <div class="rounded-circle grey lighten-2 text-center">
                      <fa icon="file-text-o"/>
                    </div>
                  </td>
                  <td>{{ contract.name }}</td>
                  <td class="blue-text">{{ contract.sentBy }}</td>
                  <td>{{ contract.date }}</td>
                  <td class="light-green-text">
                    <span v-if="contract.completed" class="light-green-text">Complete</span>
                    <span v-else class="red-text">Open</span>
                  </td>
                  <td class="td-action">
                    <btn v-if="contract.completed" class="m-0 disabled" size="sm">COMPLETEED</btn>
                    <btn v-else color="light-green" class="m-0" size="sm">COMPLETE</btn>
                  </td>
                </tr>
              </tbl-body>
            </tbl>
            <!--Pagination -->
            <div class="d-flex justify-content-start">
              <nav class="my-4 pt-2">
                <ul class="pagination pagination-rectangle pg-purple mb-0">
                  <li v-show="this.currentPage != 1" @click="previousPage()"><btn color="deep-orange lighten-1" size="sm">Previous</btn></li>
                  <li v-for="(item, index) in Array(pages)" class="page-item border ml-1" :class="{'active': currentPage == (index + 1)}" @click="movePage(index)"><a class="page-link">{{ index + 1 }}</a></li>
                  <li v-show="this.currentPage != this.pages" @click="nextPage()"><btn color="deep-orange lighten-1" size="sm">Next</btn></li>
                </ul>
              </nav>
            </div>
            <!--/Pagination -->
          </card-text>
        </card-body>
      </card>
    </div>
  </container>
</template>

<script>
import { Container, Card, CardTitle, CardBody, CardText, Tbl, TblHead, TblBody, Fa, Btn } from 'mdbvue';
import ContractsMobile from './ContractsMobile';

export default {
  name: 'Contracts',
  components: {
    Container,
    Card,
    CardTitle,
    CardBody,
    CardText,
    Tbl,
    TblHead,
    TblBody,
    Fa,
    Btn,
    ContractsMobile
  },
  props: {
    breakWidth: {
      type: Number,
      default: 770
    }
  },
  data() {
    return {
      startRow: 0,
      rowsPerPage: 10,
      currentPage: 1,
      gridData: [
        { name: 'Programme consent', sentBy: 'Nasir uddin', date: '2018-05-09', completed: false},
        { name: 'Consent for discloser', sentBy: 'Jeff Magnusson', date: '2018-05-09', completed: false},
        { name: 'Programme consent', sentBy: 'Nasir uddin', date: '2018-05-09', completed: true},
        { name: 'Consent for discloser', sentBy: 'Jeff Magnusson', date: '2018-05-09', completed: true},
        { name: 'Programme consent', sentBy: 'Nasir uddin', date: '2018-05-09', completed: true},
        { name: 'Consent for discloser', sentBy: 'Jeff Magnusson', date: '2018-05-09', completed: true},
        { name: 'Programme consent', sentBy: 'Nasir uddin', date: '2018-05-09', completed: true},
        { name: 'Consent for discloser', sentBy: 'Jeff Magnusson', date: '2018-05-09', completed: true},
        { name: 'Programme consent', sentBy: 'Nasir uddin', date: '2018-05-09', completed: true},
        { name: 'Consent for discloser', sentBy: 'Jeff Magnusson', date: '2018-05-09', completed: true},
        { name: 'Programme consent', sentBy: 'Nasir uddin', date: '2018-05-09', completed: true},
        { name: 'Consent for discloser', sentBy: 'Jeff Magnusson', date: '2018-05-09', completed: true},
        { name: 'Programme consent', sentBy: 'Nasir uddin', date: '2018-05-09', completed: true},
        { name: 'Consent for discloser', sentBy: 'Jeff Magnusson', date: '2018-05-09', completed: true},
        { name: 'Programme consent', sentBy: 'Nasir uddin', date: '2018-05-09', completed: true},
        { name: 'Consent for discloser', sentBy: 'Jeff Magnusson', date: '2018-05-09', completed: true},
        { name: 'Programme consent', sentBy: 'Nasir uddin', date: '2018-05-09', completed: true},
        { name: 'Consent for discloser', sentBy: 'Jeff Magnusson', date: '2018-05-09', completed: true},
        { name: 'Programme consent', sentBy: 'Nasir uddin', date: '2018-05-09', completed: true},
        { name: 'Consent for discloser', sentBy: 'Jeff Magnusson', date: '2018-05-09', completed: true},
        { name: 'Programme consent', sentBy: 'Nasir uddin', date: '2018-05-09', completed: true}
      ],
      isMobile: false
    };
  },
  methods: {
    movePage(index) {
      this.currentPage = index + 1;
      this.startRow = index * this.rowsPerPage;
    },
    nextPage() {
      if (this.currentPage < this.pages) {
        this.currentPage++;
        this.startRow += this.rowsPerPage;
      }
    },
    previousPage() {
      if (this.currentPage != 1) {
        this.currentPage--;
        this.startRow -= this.rowsPerPage;
      }
    },
    updatePredicate() {
      this.isMobile = window.innerWidth < this.breakWidth;
    }
  },
  computed: {
    contracts() {
      return this.gridData.slice(this.startRow, this.startRow + this.rowsPerPage);
    },
    pages() {
      return Math.floor(this.gridData.length / this.rowsPerPage) + 1;
    }
  },
  mounted() {
    this.updatePredicate();
    window.addEventListener("resize", this.updatePredicate);
  }
};
</script>

<style lang="scss" scoped>
.tbl-index {
  div {
    width: 30px;
    height: 30px;
    padding-top: 5px;
  }
  .fa {
    color: #f15d2e;
  }
}
.td-action {
  .btn {
    width: 120px;
  }
  .disabled {
    background-color: #ddd !important;
    color: grey !important;
  }
}
.pagination .btn {
  margin: 0 0 0 5px;
  height: 34px;
}
</style>
