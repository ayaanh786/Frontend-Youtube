<template>
    <footer class="efy_trans_filter">
        <a aria-label="GitHub" href="https://hussain-anime.netlify.app/" target="_blank">
            <font-awesome-icon :icon="['fab', 'github']" />
            <span v-t="'anime'" />
        </a>
    </footer>
</template>

<script>
export default {
    data() {
        return {
            donationHref: null,
            statusPageHref: null,
        };
    },
    mounted() {
        this.fetchConfig();
    },
    methods: {
        async fetchConfig() {
            this.fetchJson(this.apiUrl() + "/config").then(config => {
                this.donationHref = config?.donationUrl;
                this.statusPageHref = config?.statusPageUrl;
            });
        },
    },
};
</script>

<style>
footer {
    display: flex;
    flex-wrap: wrap;
    gap: 15rem;
    justify-content: center;
    width: 100%;
    margin: 15rem 0 0 0;
    background: var(--efy_bg1);
    border-radius: var(--efy_radius);
    padding: 15rem 5rem;
    border: var(--efy_border);
}
footer > a {
    margin: 0;
}
footer a {
    color: var(--efy_text) !important;
    -webkit-text-fill-color: var(--efy_text) !important;
    background: transparent !important;
}
</style>
