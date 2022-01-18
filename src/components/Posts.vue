<template>
</template>
<script>
import {ref, computed, onMounted} from "vue";
export default {
    name: 'Posts',
    props: {

    },
    setup() {
        const data = ref(null);
        const loading = ref(true);
        const error = ref(null);

        function fetchData() {
            loading.value = true;
            // TODO: Pass in json file name into fetch
            return fetch('../json/flyers.json', {
                method: 'get',
                headers: {
                    'content-type': 'application/json'
                }
            })
            .then(res => {
                // Throws new error with non-200 response code
                if(!res.ok) {
                    const error = new Error(res.statusText);
                    error.json = res.json();
                    throw error;
                }
                return res.json();
            })
            .then(json => {
                data.value = json.data;
            })
            .catch(err => {
                // In case of any other json related error, throws new error
                if(err.json) {
                    error.value = err;
                    return err.json.then(json => {
                        error.value.message = json.message;
                    });
                }
            })
            .then(() => {
                loading.value = false;
            });
        }

        onMounted(() => {
            fetchData();
        });

        return {
            data,
            loading,
            error
        };
    }
}
</script>
