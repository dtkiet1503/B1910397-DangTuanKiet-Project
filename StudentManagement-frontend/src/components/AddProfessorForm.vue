<script>

export default {
    props: {
        professor: { type: Object , required: true},
    },
    
    emits: ["submit:professor"],
    data(){
        return {professorLocal: this.professor}
    },
    methods: {
        submit() {
            this.$emit("submit:professor", this.professorLocal);
        },
    },
};
</script>

<template>
    <h4 class="text-center">Thêm giảng viên</h4>
    <div class="w-50 mx-auto py-4 px-5 bg-light login-form">
        <div class="mb-3">
            <label for="" class="form-label">Họ tên</label>
            <input v-model="professorLocal.name" type="text" class="form-control">
        </div>
        <div class="mb-3">
            <label for="" class="form-label">Tên tài khoản</label>
            <input v-model="professorLocal.account.username" type="text" class="form-control">
        </div>
        <div class="mb-3">
            <label for="" class="form-label">Mật khẩu</label>
            <input v-model="professorLocal.account.password" type="password" class="form-control">
        </div>
        <div class="mb-3">
            <label for="" class="form-label">Ngày sinh</label>
            <input v-model="professorLocal.birth" type="date" class="form-control">
        </div>
        <div class="mb-3">
            <label for="" class="form-label">Quê quán</label>
            <input v-model="professorLocal.hometown" type="text" class="form-control">
        </div>
        <div class="mb-3">
            <label for="" class="form-label">Số năm làm việc</label>
            <select v-model="professorLocal.unit" class="custom-select" aria-label="Default select example">
                <option value="2 năm">2 năm</option>
                <option value="3 năm">3 năm</option>
                <option value="4 năm">4 năm</option>
                <option value="5 năm">5 năm</option>
                <option value="hơn 5 năm">hơn 5 năm</option>
            </select>
        </div>
        <div class="mb-3">
            <label for="" class="form-label">Bộ phận</label>
            <select v-model="professorLocal.college" class="custom-select" aria-label="Default select example">
                <option value="Pha Chế">Pha Chế</option>
                <option value="Tạp Vụ">Tạp Vụ</option>
                <option value="Bán Hàng">Bán Hàng</option>
                <option value="Phục Vụ">Phục Vụ</option>
                <option value="Bếp">Bếp</option>
            </select>
        </div>
        <div class="d-flex justify-content-end">
            <a><button @click="submit" type="submit" class="btn btn-primary">Thêm</button></a>
        </div>
    </div>
</template>

