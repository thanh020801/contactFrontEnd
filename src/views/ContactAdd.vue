<template>
<div class="form-middle col-sm-9">
    <h1 class='col-sm-9 form-group'>Thêm Liên Hệ</h1>
        <div class="form-group col-sm-9">
            <label for="name">Tên</label>
            <input
                name="name"
                type="text"
                class="form-control"
                v-model="info.name"
            />
        </div>
        <div class="form-group  col-sm-9">
            <label for="email">E-mail</label>
            <input
                name="email"
                type="email"
                class="form-control"
                v-model="info.email"
            />
        </div>
        <div class="form-group  col-sm-9">
            <label for="address">Địa chỉ</label>
            <input
                name="address"
                type="text"
                class="form-control"
                v-model="info.address"
            />
        </div>
        <div class="form-group  col-sm-9 ">
            <label for="phone">Điện thoại</label>
            <input
                name="phone"
                type="tel"
                class="form-control"
                v-model="info.phone"
            />
        </div>

        <div class="form-group form-check  col-sm-8">
            <input
                name="favorite"
                type="checkbox"
                class="form-check-input"
                v-model="info.favorite"
            />
            <label for="favorite" class="form-check-label">
                <strong>Liên hệ yêu thích</strong>
            </label>
        </div>

        <div class="form-group form-submit  col-sm-9">
            <button class="btn btn-primary" @click='handelSubmit($event)'>Lưu</button>
        </div>
</div>
</template>

<script>
import ContactService from "@/services/contact.service";

export default {
    data() {
        return {
            info:{
                name: "",
                email:"",
                phone:"",
                address:"",
                favorite:false,
            }
        };
    },
    methods: {
        async handelSubmit(e){
            e.preventDefault()
            console.log(this.info)
            const { name, email, phone, address, favorite } = this.info
            if(!name || !email || !phone || !address ){
                alert("Yêu cầu nhập đầy đủ thông tin")
            }
            else{
                try {
                    await ContactService.create(this.info);
                    this.message = "Thêm Liên hệ thành công.";
                    alert(this.message)
                    this.$router.push('/')
                } catch (error) {
                    console.log(error);
                }                
            }

        },
    },
};
</script>
<style type="text/css">
    .form-check ,.form-submit{
        margin-left: 1rem;
    }
    .form-middle{
        margin: 0 auto;
    }
    h1{
        text-align: center;
    }
    .form-group{
        margin: 0 auto;
        padding-top: 20px;
    }
</style>