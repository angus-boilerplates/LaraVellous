<template>
    <Link v-if="isLink" :class="[sizeClass, baseClasses]">
        <slot/>
    </Link>
    <button v-bind="$attrs" v-else :class="[sizeClass, baseClasses]">
        <slot />
    </button>
</template>

<script>
export default {
    name: "PrimaryButton",
    props: {
        size: {
            default: "m",
        },
        isLink: {
            default: false,
        }
    },


    computed: {
        sizeClass() {
            switch (this.size){
                case "l":
                    return "px-3 py-2 md:py-3 md:px-5 text-md"
                case "s":
                    return "px-2 py-1 text-sm"
                default:
                    return "px-3 py-2 text-sm"
            }
        },

        baseClasses(){
            return "rounded-md font-semibold text-slate-700 shadow-sm bg-slate-200 hover:bg-slate-300 dark:bg-slate-700 dark:text-slate-100 dark:hover:bg-slate-600";
        }

    }
}


</script>

