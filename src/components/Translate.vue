<template>
    <div>
        <select class="ui compact dropdown" name="language" id="language" v-model="language">
            <option value="en">English</option>
            <option value="es">Spanish</option>
            <option value="ko">Korean</option>
            <option value="ja">	Japanese</option>
            <option value="fr">	French</option>
        </select>
        <div class="ui input">
            <input type="text" placeholder="清输入要翻译的文字" v-model="text">
        </div>
        <button v-on:click.prevent="doTranslate" class="ui green button">翻译</button>
    </div>
</template>

<script>

export default {
  name: 'translate',
    data (){
        return {
            text:'',
            language:''
        }
    },
    methods:{
        doTranslate (){
            this.$emit('translate', this.text, this.language);
        }
    },
    created (){
        this.language = 'en';
    }
}
</script>

<style>
</style>
