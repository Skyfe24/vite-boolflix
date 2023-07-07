<script>
export default {
    data() {
        return {
            searchTerm: ''
        }
    },
    props: {
        placeholder: String,
        submitLabel: String,
    },
    emits: ['term-change', 'form-submit']
};

</script>
<template>
    <div class="container">
        <H2>BOOLFLIX</H2>

        <form @submit.prevent="$emit('form-submit')">
            <input v-model.trim="searchTerm" type="text" :placeholder="placeholder || 'write here'"
                @keyup="$emit('term-change', searchTerm)">
            <button type="submit"> {{ submitLabel || 'search' }} </button>
        </form>
    </div>
</template >


<style scoped>
h2 {
    color: rgb(233, 33, 6)
}

.container {
    background-color: rgb(44, 42, 42);

}

li {

    text-transform: uppercase;
    text-decoration: none;


    color: rgb(253, 252, 252);
}

.flex {
    display: flex;
    flex-direction: row;

}

.justify-between {
    justify-content: space-between;
}
</style>