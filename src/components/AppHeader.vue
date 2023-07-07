<script>
export default {
    props: {
        placeholder: String,
        submitLabel: String,
    }
}

</script>
<template>
    <div class="container">
        <H2>BOOLFLIX</H2>

        <form>
            <input type="text" :placeholder="placeholder || 'write here'">
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
    height: 100vh;
}

li {

    text-transform: uppercase;
    text-decoration: none;


    color: grey;
}

.flex {
    display: flex;
    flex-direction: row;

}

.justify-between {
    justify-content: space-between;
}
</style>