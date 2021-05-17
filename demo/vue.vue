<template>
    <div class="newsletter-wrap">
        <div class="newspaper-title">
            <custom-icon class="custom-icon" />
            <h1>
                {{ lsTitle }}
            </h1>
        </div>
        <div>
            <h3>{{lsSubtitle}}</h3>
            <custom-btn  bg-color="lightgray" @click.native="openEl('panel')">
                {{ lsButtonText }}
            </custom-btn>
        </div>
    </div>
</template>
<script>
import NewsletterIcon from '@shiba/components/layout/custom-icon';
export default {
    name: 'CardNewsletter',
    componentName: 'CardNewsletter',
    components: {
        NewsletterIcon,
    },
    props: {
        lsTitle: {
            type: String,
            required: false,
        },
        lsSubtitle: {
            type: String,
            required: false,
        },
        lsButtonText: {
            type: String,
            default: 'subscribe to our newsletter',
        },
    },
    data() {
        return {};
    },
    methods: {
        openEl(section) {
            this.$store.commit('view/SET_ACTIVE_EL', section);
        },
    },
};
</script>
<style lang="scss" scoped>
//exception for the custom btn
.card-newsletter-wrap {
    .btn {
        padding: 1.2rem;
    }
}
</style>
