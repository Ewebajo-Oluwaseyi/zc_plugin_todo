
<template>
    <div>

        <!-- <transition name="fade">
            <edit-label-modal
                v-if="showEditModal"
                @close="showEditModal = false"
            />
        </transition>
         -->
         
        <div class="td-py-4">
            <div class="td-flex-grow td-px-4" >
                
                <SearchInput @searchTodo="searchTodo" />
                <div
      class="
        td-flex td-flex-col
        md:td-flex-row
        td-flex-start
        td-justify-start
        md:td-items-center
        md:td-justify-between
      "
    >
      <TodoNav @showLabel="showEditModal = true" />
      <AddTaskBtn @click="toggleModal" />
    </div>
            </div>
            <div class="td-px-1">
                <router-view />
            </div>
<<<<<<< HEAD:frontend/src/pages/New.vue
            
                <transition name="fade">
                    <AssignForm 
                        v-if="isAssign"
                        @toggleDeleteModal="toggleDeleteModal"
                    />
                </transition>
            <transition name="fade">
                    <TodoForm v-if="isModal" @toggleModal="toggleModal" />
                </transition>
=======

>>>>>>> 975625d623617eb1f5529089fdb547ba035f7e29:resources/js/pages/New.vue
        </div>


    </div>
</template>
<script>
import AssignForm from '../components/AssignForm';
import { mapGetters } from "vuex";
import {mapActions} from 'vuex';
import TodoForm from "../components/TodoForm";
import TodoNav from '../components/TodoNav'
import AddTaskBtn from '../components/AddTaskBtn'
import SearchInput from '../components/Search-Input'

// import TodoCard from "../components/TodoCard.vue";
export default {
    name: 'New Main',
    data() {
        return {
            isModal: false,
            
            showAll: true,
            isComment: false,
            
            showEditModal: false,
        };
    },computed: {
        ...mapGetters({
            allTodos: "todos/allTodos",
<<<<<<< HEAD:frontend/src/pages/New.vue
            isAssign: 'todos/isAssign'
=======

>>>>>>> 975625d623617eb1f5529089fdb547ba035f7e29:resources/js/pages/New.vue
        }),
    },
    methods: {
        ...mapActions({
            searchValue: 'todos/SEARCH'
        }),
        toggleModal() {
            console.log("hi");
            this.isModal = !this.isModal;
        },
        
        isMobile() {
            if (
                /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(
                    navigator.userAgent
                )
            ) {
                return true;
            } else {
                return false;
            }
        },
        showComment() {
            this.isComment = true;
        },
        hideComment() {
            this.isComment = false;
        },
        searchTodo(val) {
                this.searchValue(val);
        },
        check() {
            if (this.$route.params.id) {
                this.showComment();
            } else {
                this.hideComment();
            }
        },
    },
    components: {
        // TodoCard,
        AddTaskBtn,
        AssignForm,
        SearchInput,
        
        TodoForm,
        TodoNav
    }
}
</script>
