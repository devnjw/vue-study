<template>
    
    <div id="app">
      <ul class="todo-list">
        <v-simple-table>
          <tr v-for="(item, index) in items" :key="index">
            <td>
              <span v-on:click="enableEdit(index, true)">
                  <button v-if="! item.edit">{{item.title}}</button>
                  <input type="text" class="edit_item" v-model="item.title" v-if="item.edit" v-focus v-on:keyup.enter="enableEdit(index, false)" v-on:blur="enableEdit(index, false)">
              </span>
            </td>
          </tr>
        </v-simple-table>
      </ul>
    </div>
</template>

<script>

export default {
  el: '#app',
  data: () => ({
    items: [{
      title: 'HTML5',
    }, {
      title: 'CSS3',
    }, {
      title: 'JavaScript',
    }, ],
  }),
  
  directives: { focus: {
    inserted(el) {
        el.focus()
      },
  } },

  methods: {
    enableEdit: function(index, flag) {
      this.items[index]['edit'] = flag;
      // this.items = this.items.slice()
    },
  },
}
</script>