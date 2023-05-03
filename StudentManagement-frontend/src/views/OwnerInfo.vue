<script>

export default {
    props: {
        
    },
    emits: [],
    data(){
        return {
            
        }
    },
    methods: {
        checkRole(){
            return localStorage.getItem('uid');
        }
    },
};
</script>

<template>
    <div v-if="checkRole()!=0" class="alert alert-primary" role="alert">
        <span>Bạn đã đăng nhập với vai trò </span>
        <span v-if="checkRole()==1">Quản Trị Viên</span>
        <span v-if="checkRole()==2">Nhân Viên</span>
        <span v-if="checkRole()==3">Quản Lý</span>
    </div>

    <div v-if="checkRole()==0" class="alert alert-danger" role="alert">
        <span>Tài khoản không tồn tại</span>
    </div>

</template>

