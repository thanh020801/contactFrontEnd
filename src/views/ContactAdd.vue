<template>
    <!-- <div v-if="contact" class="page">
        <h4>Thêm mới liên hệ</h4>
        <ContactForm
            :contact="contact"
            @submit:contact="addContact"
        />
        <p>{{ message }}</p>
    </div> -->
    <div>Helo</div>
</template>

<script>
import ContactForm from "@/components/ContactForm.vue";
import ContactService from "@/services/contact.service";

export default {
    // components: {
    //     ContactForm,
    // },
    // props: {
    //     // id: { type: String, required: true },
    // },
    // data() {
    //     return {
    //         contact: null,
    //         message: "",
    //     };
    // },
    // methods: {
    //     async addContact(data) {
    //         try {
    //             await ContactService.create( data);
    //             this.message = "Thêm Liên hệ thành công.";
    //         } catch (error) {
    //             console.log(error);
    //         }
    //     },


    // },
    // created() {
    //     this.getContact(this.id);
    //     this.message = "";
    // },
};
</script>