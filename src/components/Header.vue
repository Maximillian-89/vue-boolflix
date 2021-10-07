<template>
    <header>
        <nav>
            <div class="nav-left">
                <div class="logo">
                    <img src="../assets/media/BoolFlix.png" alt="">
                </div>
            </div>
            <div class="nav-right">
                <ul>
                    <li>
                        <div class="test">
                            <div class="search-chat-contain">
                                <img @click.prevent="$emit('search', searchInput)" src="../assets/media/search-icon.svg" alt="Icona di ricerca">
                                <input type="text" @keyup.enter="$emit('search',searchInput)" placeholder="Search" v-model="searchInput">
                            </div>
                        </div>
                    </li>
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
        padding: 1rem;
        background: #000;

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
    }

    .nav-left, .nav-right {
        ul {
            display: flex;
            list-style: none;

            li {
                margin-right: 1.25rem;
            }
        }
    }

    .test {
        background: #fff;
    }
    
    .search-chat-contain {
        display: flex;
        border-bottom: 1px solid rgb(237 237 237);

        img {
            // width: 2.8rem;
            background-color: #fff;
            padding-left: 1rem;
            cursor: pointer;
        }

        input {
            outline: none;
            border: none;
            padding: 0.5rem 0.5rem 0.5rem 2rem;
            flex: 1;
            font-size: 0.938rem;
        }
    }
</style>