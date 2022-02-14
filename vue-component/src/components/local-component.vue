<template>
    <span v-on:click="enableEdit(item, true)">
        <button v-if="!edit">{{item.title}}</button>
        <input v-else type="text" class="edit_item" v-model="item.title" v-focus v-on:keyup.enter="enableEdit(item, false)" v-on:blur="enableEdit(item, false)">
    </span>
</template>

<script>
  export default {
    name: 'local-component',
    data: () => ({
        edit: false,
    }),
    props: {
        item: Object
    },
    directives: { focus: {
        inserted(el) {
            el.focus()
        },
    }},
    methods: {
        enableEdit: function(item, flag) {
            this.edit = flag;
        },
    }
  }
</script>

<style scoped>
  div {
    padding: 20px
  }

  div span {
    margin: 20px
  }
</style>