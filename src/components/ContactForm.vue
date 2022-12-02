<template>
  <Form
  @submit="submitContact"
  :validation-schema="contactFormSchema"
  >

  <div class="form-group">
  <label for="name">Tên</label>
  <Field
  name="name"
  type="text"
  class="form-control"
  v-model="contactLocal.name"
  />
  <ErrorMessage name="name" class="error-feedback" />
  </div>

  <div class="form-group">
  <label for="biensoxe">Biển kiểm soát</label>
  <Field
  name="biensoxe"
  type="text"
  class="form-control"
  v-model="contactLocal.biensoxe"
  />
  </div>

  <div class="form-group">
  <label for="tenxe">Tên xe</label>
  <Field
  name="tenxe"
  type="text"
  class="form-control"
  v-model="contactLocal.tenxe"
  />
  </div>

  <div class="form-group">
  <label for="sotien">Số tiền thế chấp</label>
  <Field
  name="sotien"
  type="text"
  class="form-control"
  v-model="contactLocal.sotien"
  />
  </div>

  <div class="form-group">
  <label for="ngay">Ngày Cầm xe</label>
  <Field
  name="ngay"
  type="date"
  class="form-control"
  v-model="contactLocal.ngay"
  />
  </div>

  <div class="form-group">
  <label for="kho">Vị trí Kho</label>
  <Field
  name="kho"
  type="text"
  class="form-control"
  v-model="contactLocal.kho"
  />
  </div>


  <div class="form-group">
  <label for="address">Địa chỉ</label>
  <Field
  name="address"
  type="text"
  class="form-control"
  v-model="contactLocal.address"
  />
  <ErrorMessage name="address" class="error-feedback" />
  </div>

  <div class="form-group">
  <label for="phone">Điện thoại</label>
  <Field
  name="phone"
  type="tel"
  class="form-control"
  v-model="contactLocal.phone"
  />
  <ErrorMessage name="phone" class="error-feedback" />
  </div>

  <div class="form-group">
  <label for="dongloi">Số tháng đã đóng</label>
  <Field
  name="dongloi"
  type="text"
  class="form-control"
  v-model="contactLocal.dongloi"
  />
  </div>

  <div class="form-group form-check">
  <input
  name="favorite"
  type="checkbox"
  class="form-check-input"
  v-model="contactLocal.favorite"
  />
  <label for="favorite" class="form-check-label">
  <strong>Đúng chủ</strong>
</label>
</div>

<div class="form-group">
<button class="btn btn-primary">Lưu</button>
<button
v-if="contactLocal._id"
type="button"
class="ml-2 btn btn-danger"
@click="deleteContact"
>
Xóa
</button>
</div>

</Form>
</template>
<script>
import * as yup from "yup";
import { Form, Field, ErrorMessage } from "vee-validate";
export default {
components: {
Form,
Field,
ErrorMessage,
},
emits: ["submit:contact", "delete:contact"],
props: {
contact: { type: Object, required: true }
},
data() {
const contactFormSchema = yup.object().shape({
name: yup
.string()
.required("Tên phải có giá trị.")
.min(2, "Tên phải ít nhất 2 ký tự.")
.max(50, "Tên có nhiều nhất 50 ký tự."),
email: yup
.string()
.email("E-mail không đúng.")
.max(50, "E-mail tối đa 50 ký tự."),
address: yup.string().max(100, "Địa chỉ tối đa 100 ký tự."),
phone: yup
.string()
.matches(
/((09|03|07|08|05)+([0-9]{8})\b)/g,
"Số điện thoại không hợp lệ."
),
});
return {
// Chúng ta sẽ không muốn hiệu chỉnh props, nên tạo biến cục bộ
// contactLocal để liên kết với các input trên form
contactLocal: this.contact,
contactFormSchema,
};
},
methods: {
submitContact() {
this.$emit("submit:contact", this.contactLocal);
},
deleteContact() {
this.$emit("delete:contact", this.contactLocal.id);
},
},
};
</script>
<style scoped>
@import "@/assets/form.css";
</style>    