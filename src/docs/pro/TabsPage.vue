<template>
  <container class="mt-5">
    <h2 class="mb-4">Basic</h2>
    <tab tabs justify>
        <tab-item :active="basic1==1" @click.native.prevent="basic1 = 1">Profile</tab-item>
        <tab-item :active="basic1==2" @click.native.prevent="basic1 = 2">Follow</tab-item>
        <tab-item :active="basic1==3" @click.native.prevent="basic1 = 3">Contact</tab-item>
    </tab>
    <tab-content class="mb-5 card">
      <transition-group name="slide-toggle">
        <tab-pane key="show1" v-show="basic1==1"><br/>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nihil odit magnam minima, soluta doloribus reiciendis molestiae placeat unde eos molestias. Quisquam aperiam, pariatur. Tempora, placeat ratione porro voluptate odit minima.</tab-pane>
        <tab-pane key="show2" v-show="basic1==2"><br/>Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. <br><br>Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. </tab-pane>
        <tab-pane key="show3" v-show="basic1==3"><br/>At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident, similique sunt in culpa qui officia deserunt mollitia animi, id est laborum et dolorum fuga. <br><br>Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi optio cumque nihil impedit quo minus id quod maxime placeat facere possimus, omnis voluptas assumenda est, omnis dolor repellendus. Temporibus autem quibusdam et aut officiis debitis aut rerum necessitatibus saepe eveniet ut et voluptates repudiandae sint et molestiae non recusandae. Itaque earum rerum hic tenetur a sapiente delectus, ut aut reiciendis voluptatibus maiores alias consequatur aut perferendis doloribus asperiores repellat.</tab-pane>
      </transition-group>
    </tab-content>

    <tab tabs color="indigo" justify>
        <tab-item icon="user" :active="basic2==1" @click.native.prevent="basic2=1">Profile</tab-item>
        <tab-item icon="heart" :active="basic2==2" @click.native.prevent="basic2=2">Follow</tab-item>
        <tab-item icon="envelope" :active="basic2==3" @click.native.prevent="basic2=3">Mail</tab-item>
    </tab>
    <tab-content class="card">
      <transition-group name="slide-toggle">
        <tab-pane key="show4" v-show="basic2==1"><br/>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nihil odit magnam minima, soluta doloribus reiciendis molestiae placeat unde eos molestias. Quisquam aperiam, pariatur. Tempora, placeat ratione porro voluptate odit minima.</tab-pane>
        <tab-pane key="show5" v-show="basic2==2"><br/>Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. <br><br>Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. </tab-pane>
        <tab-pane key="show6" v-show="basic2==3"><br/>At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident, similique sunt in culpa qui officia deserunt mollitia animi, id est laborum et dolorum fuga. <br><br>Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi optio cumque nihil impedit quo minus id quod maxime placeat facere possimus, omnis voluptas assumenda est, omnis dolor repellendus. Temporibus autem quibusdam et aut officiis debitis aut rerum necessitatibus saepe eveniet ut et voluptates repudiandae sint et molestiae non recusandae. Itaque earum rerum hic tenetur a sapiente delectus, ut aut reiciendis voluptatibus maiores alias consequatur aut perferendis doloribus asperiores repellat.</tab-pane>
      </transition-group>
    </tab-content>

    <hr class="my-5">

    <h2 class="mb-4">Pills</h2>
    <tab pills color="secondary" justify>
      <tab-item :active="pills==1" @click.native.prevent="pills=1">Active</tab-item>
      <tab-item :active="pills==2" @click.native.prevent="pills=2">Link</tab-item>
      <tab-item :active="pills==3" @click.native.prevent="pills=3">Link</tab-item>
      <tab-item :active="pills==4" @click.native.prevent="pills=4">Help</tab-item>
    </tab>
    <tab-content class="mb-5">
      <transition-group name="slide-toggle">
        <tab-pane key="pills1" v-show="pills==1">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nihil odit magnam minima, soluta doloribus reiciendis molestiae placeat unde eos molestias. Quisquam aperiam, pariatur. Tempora, placeat ratione porro voluptate odit minima.</tab-pane>
        <tab-pane key="pills2" v-show="pills==2">Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. <br><br>Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. </tab-pane>
        <tab-pane key="pills3" v-show="pills==3">At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident, similique sunt in culpa qui officia deserunt mollitia animi, id est laborum et dolorum fuga. <br><br>Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi optio cumque nihil impedit quo minus id quod maxime placeat facere possimus, omnis voluptas assumenda est, omnis dolor repellendus. Temporibus autem quibusdam et aut officiis debitis aut rerum necessitatibus saepe eveniet ut et voluptates repudiandae sint et molestiae non recusandae. Itaque earum rerum hic tenetur a sapiente delectus, ut aut reiciendis voluptatibus maiores alias consequatur aut perferendis doloribus asperiores repellat.</tab-pane>
        <tab-pane key="pills4" v-show="pills==4">Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi optio cumque nihil impedit quo minus id quod maxime placeat facere possimus, omnis voluptas assumenda est, omnis dolor repellendus. Temporibus autem quibusdam et aut officiis debitis aut rerum necessitatibus saepe eveniet ut et voluptates repudiandae sint et molestiae non recusandae. Itaque earum rerum hic tenetur a sapiente delectus, ut aut reiciendis voluptatibus maiores alias consequatur aut perferendis doloribus asperiores repellat.</tab-pane>
      </transition-group>
    </tab-content>



    <h2 class="mb-4">Vertical pills</h2>
    <row class="mb-5">
      <column md="3">
        <tab pills color="primary" vertical>
          <tab-item :active="vertical==1" @click.native.prevent="vertical=1">Downloads <fa icon="download" class="ml-2"/></tab-item>
          <tab-item :active="vertical==2" @click.native.prevent="vertical=2">Orders & Invoices <fa icon="file" class="ml-2"/></tab-item>
          <tab-item :active="vertical==3" @click.native.prevent="vertical=3">Billing Details <fa icon="address-card" class="ml-2"/></tab-item>
        </tab>
      </column>
      <column md="9">
        <tab-content vertical>
          <transition-group name="slide-toggle">
            <tab-pane key="pills1" v-show="vertical==1"><h5 class="my-2 h5">Panel 1</h5></tab-pane>
            <tab-pane key="pills2" v-show="vertical==2"><h5 class="my-2 h5">Panel 2</h5></tab-pane>
            <tab-pane key="pills3" v-show="vertical==3"><h5 class="my-2 h5">Panel 3</h5></tab-pane>
          </transition-group>
        </tab-content>
      </column>
    </row>

    <h2 class="mb-4">Pills within the tabs</h2>

    <tab tabs color="indigo" justify>
      <tab-item icon="user" :active="basicOutside==1" @click.native.prevent="basicOutside=1">Profile</tab-item>
      <tab-item icon="heart" :active="basicOutside==2" @click.native.prevent="basicOutside=2">Follow</tab-item>
    </tab>
    <tab-content>
      <transition-group name="slide-toggle">
        <tab-pane key="show5" v-show="basicOutside==1">
          <row>
            <column md="3">
              <tab pills color="primary" vertical>
                <tab-item :active="verticalWithin==1" @click.native.prevent="verticalWithin=1">Downloads <fa icon="download" class="ml-2"/></tab-item>
                <tab-item :active="verticalWithin==2" @click.native.prevent="verticalWithin=2">Orders & Invoices <fa icon="file" class="ml-2"/></tab-item>
                <tab-item :active="verticalWithin==3" @click.native.prevent="verticalWithin=3">Billing Details <fa icon="address-card" class="ml-2"/></tab-item>
              </tab>
            </column>
            <column md="9">
              <tab-content vertical>
                <transition-group name="slide-toggle">
                  <tab-pane key="pills1" v-show="verticalWithin==1"><h5 class="my-2 h5">Panel 1</h5></tab-pane>
                  <tab-pane key="pills2" v-show="verticalWithin==2"><h5 class="my-2 h5">Panel 2</h5></tab-pane>
                  <tab-pane key="pills3" v-show="verticalWithin==3"><h5 class="my-2 h5">Panel 3</h5></tab-pane>
                </transition-group>
              </tab-content>
            </column>
          </row>
        </tab-pane>
        <tab-pane key="show6" v-show="basicOutside==2"><br/>At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident, similique sunt in culpa qui officia deserunt mollitia animi, id est laborum et dolorum fuga. <br><br>Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi optio cumque nihil impedit quo minus id quod maxime placeat facere possimus, omnis voluptas assumenda est, omnis dolor repellendus. Temporibus autem quibusdam et aut officiis debitis aut rerum necessitatibus saepe eveniet ut et voluptates repudiandae sint et molestiae non recusandae. Itaque earum rerum hic tenetur a sapiente delectus, ut aut reiciendis voluptatibus maiores alias consequatur aut perferendis doloribus asperiores repellat.</tab-pane>
      </transition-group>
    </tab-content>

    <hr class="my-5">

    <h2 class="mb-4">Classic tabs</h2>

    <tab classicTabs color="cyan">
      <tab-item :active="classic1==1" @click.native.prevent="classic1 = 1">Profile</tab-item>
      <tab-item :active="classic1==2" @click.native.prevent="classic1 = 2">Follow</tab-item>
      <tab-item :active="classic1==3" @click.native.prevent="classic1 = 3">Contact</tab-item>
      <tab-item :active="classic1==4" @click.native.prevent="classic1 = 4">Be awesome</tab-item>
    </tab>
    <tab-content class="mb-5 card">
      <transition-group name="slide-toggle">
        <tab-pane key="show1" v-show="classic1==1">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nihil odit magnam minima, soluta doloribus reiciendis molestiae placeat unde eos molestias. Quisquam aperiam, pariatur. Tempora, placeat ratione porro voluptate odit minima.</tab-pane>
        <tab-pane key="show2" v-show="classic1==2">Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. <br><br>Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. </tab-pane>
        <tab-pane key="show3" v-show="classic1==3">At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident, similique sunt in culpa qui officia deserunt mollitia animi, id est laborum et dolorum fuga. <br><br>Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi optio cumque nihil impedit quo minus id quod maxime placeat facere possimus, omnis voluptas assumenda est, omnis dolor repellendus. Temporibus autem quibusdam et aut officiis debitis aut rerum necessitatibus saepe eveniet ut et voluptates repudiandae sint et molestiae non recusandae. Itaque earum rerum hic tenetur a sapiente delectus, ut aut reiciendis voluptatibus maiores alias consequatur aut perferendis doloribus asperiores repellat.</tab-pane>
        <tab-pane key="show4" v-show="classic1==4">Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi optio cumque nihil impedit quo minus id quod maxime placeat facere possimus, omnis voluptas assumenda est, omnis dolor repellendus. Temporibus autem quibusdam et aut officiis debitis aut rerum necessitatibus saepe eveniet ut et voluptates repudiandae sint et molestiae non recusandae. Itaque earum rerum hic tenetur a sapiente delectus, ut aut reiciendis voluptatibus maiores alias consequatur aut perferendis doloribus asperiores repellat.</tab-pane>
      </transition-group>
    </tab-content>

    <tab classicTabs color="orange">
      <tab-item :active="classic2==1" @click.native.prevent="classic2 = 1"><fa icon="user" size="2x"/><br/>Profile</tab-item>
      <tab-item :active="classic2==2" @click.native.prevent="classic2 = 2"><fa icon="heart" size="2x"/><br/>Follow</tab-item>
      <tab-item :active="classic2==3" @click.native.prevent="classic2 = 3"><fa icon="envelope" size="2x"/><br/>Contact</tab-item>
      <tab-item :active="classic2==4" @click.native.prevent="classic2 = 4"><fa icon="star" size="2x"/><br/>Be awesome</tab-item>
    </tab>
    <tab-content class="mb-5 card">
      <transition-group name="slide-toggle">
        <tab-pane key="show1" v-show="classic2==1">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nihil odit magnam minima, soluta doloribus reiciendis molestiae placeat unde eos molestias. Quisquam aperiam, pariatur. Tempora, placeat ratione porro voluptate odit minima.</tab-pane>
        <tab-pane key="show2" v-show="classic2==2">Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. <br><br>Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. </tab-pane>
        <tab-pane key="show3" v-show="classic2==3">At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident, similique sunt in culpa qui officia deserunt mollitia animi, id est laborum et dolorum fuga. <br><br>Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi optio cumque nihil impedit quo minus id quod maxime placeat facere possimus, omnis voluptas assumenda est, omnis dolor repellendus. Temporibus autem quibusdam et aut officiis debitis aut rerum necessitatibus saepe eveniet ut et voluptates repudiandae sint et molestiae non recusandae. Itaque earum rerum hic tenetur a sapiente delectus, ut aut reiciendis voluptatibus maiores alias consequatur aut perferendis doloribus asperiores repellat.</tab-pane>
        <tab-pane key="show4" v-show="classic2==4">Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi optio cumque nihil impedit quo minus id quod maxime placeat facere possimus, omnis voluptas assumenda est, omnis dolor repellendus. Temporibus autem quibusdam et aut officiis debitis aut rerum necessitatibus saepe eveniet ut et voluptates repudiandae sint et molestiae non recusandae. Itaque earum rerum hic tenetur a sapiente delectus, ut aut reiciendis voluptatibus maiores alias consequatur aut perferendis doloribus asperiores repellat.</tab-pane>
      </transition-group>
    </tab-content>

  </container>
</template>

<script>
import { Tab, TabItem, TabContent, TabPane, Container, Column, Row, Fa } from 'mdbvue';

export default {
  name: 'TabPage',
  components: {
    Tab,
    TabItem,
    TabContent,
    TabPane,
    Container,
    Column,
    Row,
    Fa
  },
  data() {
    return {
      basic1: '1',
      basic2: '1',
      pills: '1',
      vertical: '1',
      basicOutside: '1',
      verticalWithin: '1',
      classic1: '1',
      classic2: '1'
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.slide-toggle-enter-active {
  transition: .3s ease-in;
  opacity: 1;
  max-height: 500px;
}
.slide-toggle-enter,
.slide-toggle-leave-active {
  opacity: 0;
  max-height: 0;
}
.slide-toggle-leave {
  opacity: 1;
  max-height: 500px;
}
</style>
