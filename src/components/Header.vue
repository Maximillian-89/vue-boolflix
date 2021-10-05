<template>
    <header>
        <nav>
            <div class="nav-left">
                <ul>
                    <li></li>
                    <li></li>
                    <li></li>
                    <li></li>
                    <li></li>
                    <li></li>
                </ul>
            </div>
            <div class="nav-right">
                <ul>
                    <li>
                        <form>
                            <input type="text" placeholder="Search" v-model="searchInput">
                            <button type="submit" @click.prevent="$emit('search', searchInput)">Search</button>
                            <button @click.prevent="resetSearch()">Reset</button>
                        </form>
                    </li>
                    <li></li>
                    <li></li>
                </ul>
            </div>
        </nav>
    </header>
</template>

<script>
    export default {
        name: 'Header',
        
        data() {
        return {
            searchInput: ''
        }
    },

    methods : {
        resetSearch() {
            this.searchInput = '';
            this.$emit('search', this.searchInput);
        }
    }
}
</script>

<style lang="scss" scoped>
    header {
        height: 4.375rem;
        // background: rgb(20, 20, 20);

        nav {
            // width: 98%;
            display: flex;
            justify-content: space-between;
        }
    }

    .nav-left, .nav-right {
        ul {
            display: flex;

            li {
                margin-right: 1.25rem;
            }
        }
    }
</style>