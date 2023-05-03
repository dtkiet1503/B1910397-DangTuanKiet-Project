<script>

export default {
    props: {
        classes: { type: Object , required: true},
    },
    
    emits: ["submit:class"],
    data(){
        return {classLocal: this.classes}
    },
    methods: {
        submit() {
            this.$emit("submit:class", this.classLocal);
        },
    },
};
</script>

<template>
    <h4 class="text-center">Thêm ca làm</h4>
    <div class="w-50 mx-auto py-4 px-5 bg-light login-form">
        <div class="mb-3">
            <label for="" class="form-label">Ca làm việc</label>
            <select v-model="classLocal.subject" class="custom-select" aria-label="Default select example">
                <option value="Ca Sáng">Ca Sáng</option>
                <option value="Ca Trưa">Ca Trưa</option>
                <option value="Ca Sáng">Ca Tối</option>
            </select>
        </div>
        <div class="mb-3">
            <label for="" class="form-label">Ký hiệu</label>
            <input v-model="classLocal.name" type="text" class="form-control">
        </div>
        <div class="mb-3">
            <label for="" class="form-label">Thứ</label>
            <select v-model="classLocal.day" class="custom-select" aria-label="Default select example">
                <option value="Thứ hai">Thứ hai</option>
                <option value="Thứ ba">Thứ ba</option>
                <option value="Thứ tư">Thứ tư</option>
                <option value="Thứ năm">Thứ năm</option>
                <option value="Thứ sáu">Thứ sáu</option>
                <option value="Thứ bảy">Thứ bảy</option>
                <option value="Chủ nhật">Chủ nhật</option>
            </select>
        </div>
        <div class="mb-3">
            <label for="" class="form-label">Phòng</label>
            <select v-model="classLocal.room" class="custom-select" aria-label="Default select example">
                <option value="Phòng 101">Phòng 101</option>
                <option value="Phòng 102">Phòng 102</option>
                <option value="Phòng 302">Phòng 302</option>
                <option value="Phòng 201">Phòng 201</option>
                <option value="Phòng 205">Phòng 205</option>
                <option value="Phòng 202">Phòng 202</option>
            </select>
        </div>
        <div class="mb-3">
            <label for="" class="form-label">Ca</label>
            <select v-model="classLocal.time" class="custom-select" aria-label="Default select example">
                <option value="Ca 1(7h-9h)">Ca 1(7h-9h)</option>
                <option value="Ca 2(9h-11h)">Ca 2(9h-11h)</option>
                <option value="Ca 3(11h-1h)">Ca 3(11h-1h)</option>
                <option value="Ca 4(1-3h)">Ca 4(1h-3h)</option>
                <option value="Ca 5(3h-5h)">Ca 5(5h-7h)</option>
                <option value="Ca 6(7h-9h)">Ca 6(7h-9h)</option>
            </select>
        </div>
        <div class="mb-3">
            <label for="" class="form-label">Số giờ làm</label>
            <input v-model="classLocal.long" type="number" class="form-control">
        </div>
        
        <div class="d-flex justify-content-end">
            <a><button @click="submit" type="submit" class="btn btn-primary">Thêm</button></a>
        </div>
    </div>
</template>

