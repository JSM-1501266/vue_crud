<template>
    <div>
        <h1>게시판</h1>
        <table border="2" style="margin: auto">
            <tr>
                <td>글쓴이</td>
                <td>제목</td>
                <td>내용</td>
            </tr>
            <tr :key="index" v-for="(value, index) in data" @click="detail(index)">
                <td>{{value.writer}}</td>
                <td>{{value.title}}</td>
                <td>{{value.content}}</td>
            </tr>
        </table> 
        <br />
        <button @click="write">글쓰기</button>
    </div>
</template>

<script>
import data from '@/data'

export default {
    name: 'Read',
    data() {
        return {
            data: data
        }
    },
    methods: {
        write() {
            this.$router.push({
                name: 'Create'
            })
        },
        detail(index) {
            this.$router.push({
                name: 'Detail',
                params: {
                    contentId: index
                }
            })
        }
    }
}
</script> 