<template>
    <div
        id="main_view"
        class="section_grid td-p-2"
    >
        <div>
            <template v-if="showAll">
                <div v-if="allTodos.length <= 0">
                    <Empty
                        :title="'Oops Your Todo Store is Empty'"
                        :subtitle="'Click Create Task Button'"
                    />
                </div>
                <div
                    v-else
                    class="
                         todo_container
<<<<<<< HEAD:resources/js/pages/Main.vue
 sm:grid sm:grid-cols-2
gap-4
 md:grid-cols-3
 lg:grid-cols-4
<<<<<<< HEAD:frontend/src/pages/Main.vue
=======
 sm:td-grid sm:td-grid-cols-2
td-gap-4
 md:td-grid-cols-3
 lg:td-grid-cols-4 
>>>>>>> da68dc87121fa18bbaaca7fccced105b69497dc6:frontend/src/pages/Main.vue
=======
>>>>>>> 975625d623617eb1f5529089fdb547ba035f7e29:resources/js/pages/Main.vue
                    "
                >
                    <NewCard
                        v-for="(todo, index) in allTodos"
                        :key="index++"
                        :todo="todo"
                    />
        </div>
        </template>
        <template v-else>
            <div class="
                        todo_container
                        sm:td-grid sm:td-grid-cols-2
                        td-gap-4
                        md:td-grid-cols-3
                        lg:td-grid-cols-4
                    ">
                <NewCard
                    v-for="(todo, index) in result"
                    :key="index"
                    :todo="todo"
                   
                />
            </div>
        </template>
        </div>
        </div>
</template>
<script>
import Empty from "../components/Empty.vue";
import NewCard from "../components/Newcard.vue";
import { mapGetters } from "vuex";
import { mapActions } from "vuex";
export default {
  name: "Main",
  data() {
    return {};
  },
  computed: {
    ...mapGetters({
      allTodos: "todos/allTodos",
      result: "todos/searchedTodo",
      showAll: "todos/showAll",
    }),
  },
  methods: {
       ...mapActions({getAllTodos: "todos/getAllTodos"}),
       
  },
  components: {
    NewCard,
    Empty,
  },
  mounted() {
    this.getAllTodos();
  }
};
</script>
<style lang="scss"></style>
