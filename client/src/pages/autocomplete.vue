<template>
    <section>
        <p class="content"><b><h3>Auto-complete</h3></b></p>
        <b-field label="Use Auto-complete">
            <b-autocomplete
                rounded
                v-model="name"
                :data="filteredDataArray"
                placeholder="e.g. Tasker"
                clearable
                @select="option => selected = option">
                <template slot="empty">404 Not found</template>
            </b-autocomplete>
        </b-field>
    </section>
</template>

<script>
    export default {
        data() {
            return {
                data: [
                    'final',
                    'vue',
                    'dodge',
                    'demon',
                    'SRT',
                    'hellcat',
                    'chandu@gmail.com',
                    'sekhar@gmail.com',
                    '2022',
                    'abc',
                    'New paltz',
                    'New York',
                    'Albany',
                    'ulster'
                ],
                name: '',
                selected: null
            }
        },
        computed: {
            filteredDataArray() {
                return this.data.filter((option) => {
                    return option
                        .toString()
                        .toLowerCase()
                        .indexOf(this.name.toLowerCase()) >= 0
                })
            }
        }
    }
</script>