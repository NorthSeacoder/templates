
<template>
    <yqg-static-form
        title="详情"
        :options="DetailFormOptions"
        :values="record"
    />
</template>

<script type="text/babel">
import {modal} from 'src/common/mixin';

import {DetailFormOptions} from '../constant/options';

export default {
    name: 'DetailModal',

    onlyClose: true,

    mixins: [modal],

    props: {
        record: {
            type: Object,
            default: () => ({})
        }
    },

    data() {
        return {
            DetailFormOptions
        };
    }
};
</script>
