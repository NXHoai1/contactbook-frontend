<script>

export default {
props: {
contact: { type: Object, required: true },
},
};
</script>
<template>
<div>
<div class="p-1">
<strong>Tên:</strong>
{{ contact.name }}
</div>

<div class="p-1">
<strong>Biển kiểm soát:</strong>
{{ contact.biensoxe }}
</div>

<div class="p-1">
<strong>Tên xe:</strong>
{{ contact.tenxe }}
</div>

<div class="p-1">
<strong>Số tiền thế chấp:</strong>
{{ contact.sotien }}<strong> vnđ</strong>
</div>

<div class="p-1">
<strong>Ngày cầm xe:</strong>
{{ contact.ngay }}
</div>

<div class="p-1">
<strong>Kho chứa số:</strong>
{{ contact.kho }}
</div>

<div class="p-1">
<strong>Địa chỉ:</strong>
{{ contact.address }}
</div>

<div class="p-1">
<strong>Điện thoại:</strong>
{{ contact.phone }}
</div>

<div class="p-1">
<strong>Đã đóng </strong>
{{ contact.dongloi }}
<strong>tháng</strong>
</div>

<div class="p-1">
<strong>Xe đúng chủ:&nbsp;</strong>
<i v-if="contact.favorite" class="fas fa-check"></i>



<i v-else class="fas fa-times"></i>
</div>
</div>
</template>
