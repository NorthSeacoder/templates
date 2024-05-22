
<template>
    <yqg-simple-form
        :title="title"
        :options="EditModalFormOptions"
        :values="record"
        @confirm="onConfirm"
        @cancel="dismiss"
    />
</template>

<script type="text/babel">

import {modal} from 'src/common/mixin';
import Xxx from 'src/common/resource/xxx';

import {EditModalFormOptions} from '../constant/options';

export default {
    name: 'EditModal',

    mixins: [modal],

    inject: ['opSuccess'],

    props: {
        record: {
            type: Object,
            default: () => ({})
        }
    },

    data() {
        return {
            EditModalFormOptions,
        };
    },

    computed: {
        title() {
            return this.record.id ? '编辑' : '创建';
        }
    },

    methods: {
        async onConfirm({record}) {
            await Xxx.save(record);
            this.opSuccess();
            this.close();
        }
    }
};
</script>
