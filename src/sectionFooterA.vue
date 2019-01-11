<template>
    <div class="footer_A">
        <!-- wwManager:start -->
        <wwSectionEditMenu v-bind:sectionCtrl="sectionCtrl"></wwSectionEditMenu>
        <!-- wwManager:end -->

        <wwObject class="background" v-bind:ww-object="section.data.background" ww-category="background"></wwObject>

        <div class="venue-info">
            <div class="container">
                <div class="row venue-info-container">
                    <wwObject class="block" v-bind:ww-object="section.data.text1"></wwObject>
                    <wwObject class="block" v-bind:ww-object="section.data.text2"></wwObject>
                    <wwObject class="block" v-bind:ww-object="section.data.text3"></wwObject>
                </div>
            </div>
        </div>

    </div>
</template>

<script>
export default {
    name: "footer_A",
    props: {
        sectionCtrl: Object
    },
    data() {
        return {}
    },
    computed: {
        section() {
            return this.sectionCtrl.get();
        }
    },
    created() {
        this.section.data = this.section.data || {}
        
        if (!this.section.data.background) {
            this.section.data.background = wwLib.wwObject.getDefault({ type: 'ww-color' });
        }
        if (!this.section.data.text1) {
            this.section.data.text1 = wwLib.wwObject.getDefault({ type: 'ww-text' });
        }
        if (!this.section.data.text2) {
            this.section.data.text2 = wwLib.wwObject.getDefault({ type: 'ww-text' });
        }
        if (!this.section.data.text3) {
            this.section.data.text3 = wwLib.wwObject.getDefault({ type: 'ww-text' });
        }
        this.sectionCtrl.update(this.section);
    },
    methods: {}
};
</script>

<style scoped>
.footer_A {
    position: relative;
}

.footer_A .social {
    display: table;
    width: 100%;
    height: 70px;
}

.footer_A .background {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
}

.footer_A .social-container {
    display: table-cell;
    text-align: center;
    vertical-align: middle;
}

.footer_A .social a {
    text-decoration: none;
    color: white;
}

.footer_A .social a div {
    font-size: 25px;
    border: 4px solid white;
    border-radius: 100%;
    padding: 5px;
    width: 50px;
    height: 50px;
    text-align: center;
    display: inline-block;
}

.footer_A .social-icon {
    padding-top: 10px;
    height: 70px;
}

.footer_A .venue-info {
    padding-top: 20px;
    padding-bottom: 20px;
}

.footer_A .venue-info-container>div {
    text-align: center;
    margin-bottom: 10px;
}

.footer_A .section-edit {
    top: 5px !important;
}

.footer_A .row {
    display: -ms-flexbox;
    display: flex;
    -ms-flex-wrap: wrap;
    flex-wrap: wrap;
    margin-right: -15px;
    margin-left: -15px;
}

.footer_A .block {
    position: relative;
    width: 100%;
    min-height: 1px;
    padding-right: 15px;
    padding-left: 15px;
    -ms-flex: 0 0 100%;
    flex: 0 0 100%;
    max-width: 100%;
}

@media (min-width: 480px) {
    .footer_A .block {
        -ms-flex: 0 0 33.333333%;
        flex: 0 0 33.333333%;
        max-width: 33.333333%;
    }
}

@media (min-width: 768px) {}

@media (min-width: 992px) {}

@media (min-width: 1200px) {}
</style>
