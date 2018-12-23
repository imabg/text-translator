<template>
    <div class="container">
        <form @submit.prevent>
            <div class="form-group">
                <label for="exampleFormControlTextarea1">Type your Text✍</label>
                <textarea class="form-control" id="exampleFormControlTextarea1" rows="3" placeholder="Enter Text ...." v-model="text"></textarea>
            </div>
            <div class="form-group">
                <label for="exampleFormControlSelect1">Choose Language</label>
                <select class="form-control" id="exampleFormControlSelect1" v-model="selectedLang" >
                <option value="de">German</option>
                <option value="en">English</option>
                <option value="pa">Punjabi</option>
                <option value="ru">Russian</option>
                <option value="hi">Hindi</option>
                <option value="ml">Malayalam</option>
                <option value="ar">Arabic</option>
                <option value="fr">French</option>
                <option value="bn">Bengali</option>
                </select>
            </div>
            <button class="btn btn-primary" @click="translateText">Convert</button>
        </form>
        <translateText :cnvrtText = "cnvrtText"/>
    </div>
</template>

<script>
import axios from 'axios';
import translateText from '../components/translatedText.vue';

export default {
    name: 'translator',
    components: {
        translateText
    },
    data() {
        return {
            text: '',
            selectedLang: '',
            cnvrtText: ''
        }
    },
    created() {
        this.text = 'Merry Chrismas'
        this.selectedLang = 'hi'
    },
    methods: {
        translateText() {
            axios.get(`https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20181222T183038Z.81f871b57735deea.1dad18de52bfb7302fe179a8105a178c868f617b
            &text=${this.text}&lang=${this.selectedLang}`)
            .then(res => {
                this.cnvrtText = res.data.text["0"];
            })
            .catch(err => console.log(err));
        }
    }
}
</script>
