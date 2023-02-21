<script>


export default {
    props: {
        text: {
            type: String,
            default: "button",
        },
        event: {
            type: String,
        }
    },
};

</script>


<template>
    <button @click="$emit(event)" class="mt-4 h-10 w-28 hover:w-32 text-white bg-orange-700 rounded hover:rounded-3xl transition-all">
        {{ text }}
    </button>
</template>