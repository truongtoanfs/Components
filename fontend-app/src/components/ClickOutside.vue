<template>
<h1 class="mx-auto font-bold py-4 text-2xl">Click outside with custom directive</h1>
    <div>   
        <button ref="button" @click="isOpenList = !isOpenList" class="bg-gray-300 px-3 py-1 mb-3 rounded">Open Detail</button>

        <transition leave-active-class="transition ease-in duration-100" leave-from-class="opacity-100" leave-to-class="opacity-0">
            <ul class="bg-pink-400 text-white" v-click-outside="{ exclude: ['button'], handler: 'closeDropdown' }" v-if="isOpenList">
                <li class="relative py-1.5 px-2 cursor-default select-none">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Repellat, vero doloribus esse soluta ipsum nisi. Voluptas vel eligendi nam quidem repellendus eos velit. Et dolore harum labore ipsa debitis deserunt!
                </li>
                <li class="relative py-1.5 px-2 cursor-default select-none">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Repellat, vero doloribus esse soluta ipsum nisi. Voluptas vel eligendi nam quidem repellendus eos velit. Et dolore harum labore ipsa debitis deserunt!
                </li>
                <li class="relative py-1.5 px-2 cursor-default select-none">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Repellat, vero doloribus esse soluta ipsum nisi. Voluptas vel eligendi nam quidem repellendus eos velit. Et dolore harum labore ipsa debitis deserunt!
                </li>
            </ul>
        </transition>
    </div>
</template>
<script>
import { ref } from 'vue';

export default {
    setup() {
        function test() {
            console.log('here');
        }
        function closeDropdown() {
            isOpenList.value = false;
        }
        const isOpenList = ref(false);
        const selectedItem = ref('');
        return {
            isOpenList,
            selectedItem,
            test,
            closeDropdown
        }
    }
}
</script>
