<template>
    <div>
        test 123
        asaDAS
    </div>
</template>

<script>
import { FormField, HandlesValidationErrors } from 'laravel-nova';

export default {
    mixins: [FormField, HandlesValidationErrors],

    props: ['resourceName', 'resourceId', 'field'],

    methods: {
    /*
     * Set the initial, internal value for the field.
     */
        setInitialValue() {
            this.value = this.field.value || '';
        },

        /**
     * Fill the given FormData object with the field's internal value.
     */
        fill(formData) {
            formData.append(this.field.attribute, this.value || '');
        },
    },
};
</script>
