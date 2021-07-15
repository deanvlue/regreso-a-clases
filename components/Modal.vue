<template>
  <div>
    <b-modal :ref="ref" :id="ref" hide-header hide-footer centered :size="size">
      <div :class="'modal-title ' + variant">
        <strong>{{ title }}</strong>
      </div>
      <b-container>
        <slot></slot>
      </b-container>
    </b-modal>
  </div>
</template>
<script>
export default {
  props: ["ref", "title", "variant", "size"]
};
</script>
<style>
.modal-content {
  border: 5px solid #825333;
  margin-top: 30px;
}
.modal-body {
  background: #f9f9dd;
  border: 10px solid #d6b080;
}
.modal-body .container {
  border: 2px dashed #dab182;
}
.modal-title {
  background: #6c49b8;
  color: #ffffff;
  white-space: nowrap;
  padding: 1rem 0rem;

  position: absolute;
  top: -45px;
  left: 50%;
  transform: translate(-50%, 0);
  padding: 1rem 0.5rem;

  border-radius: 1rem 1rem 2rem 2rem;
}
.modal-title strong {
  border: 2px solid #ffffff;
  padding: 0.5rem 2rem;

  border-radius: 1rem 1rem 2rem 2rem;
}
.modal-close {
  position: absolute;
  width: 30px;
  height: 30px;
  right: -20px;
  top: -20px;
  color: #ffffff;
  text-align: center;
  line-height: 29px;
  font-size: 15px;
  border-radius: 100%;
  background: #be3365;
  border: 1px solid #a32755;
  cursor: pointer;
}
.green {
  background: rgb(155, 195, 85);
  background: linear-gradient(
    0deg,
    rgba(155, 195, 85, 1) 0%,
    rgba(123, 168, 56, 1) 50%,
    rgba(155, 195, 85, 1) 100%
  );
}
.green strong {
  border: 2px solid #eac858;
}
.darkgreen {
  background: #0c6259;
  background: linear-gradient(
    186.52deg,
    #0c6259 -1.25%,
    #0c6259 46.11%,
    #06312d 96.98%
  );
}
.darkgreen strong {
  border: 2px solid #ffffff;
}
.blue {
  background: rgb(34, 88, 128);
  background: linear-gradient(
    0deg,
    rgba(34, 88, 128, 1) 0%,
    rgba(30, 77, 111, 1) 50%,
    rgba(34, 88, 128, 1) 100%
  );
}
.blue strong {
  border: 2px solid #3f9086;
}
.purple {
  background: rgb(102, 49, 103);
  background: -moz-linear-gradient(
    0deg,
    rgba(102, 49, 103, 1) 26%,
    rgba(68, 32, 68, 1) 47%,
    rgba(102, 49, 103, 1) 84%
  );
  background: -webkit-linear-gradient(
    0deg,
    rgba(102, 49, 103, 1) 26%,
    rgba(68, 32, 68, 1) 47%,
    rgba(102, 49, 103, 1) 84%
  );
  background: linear-gradient(
    0deg,
    rgba(102, 49, 103, 1) 26%,
    rgba(68, 32, 68, 1) 47%,
    rgba(102, 49, 103, 1) 84%
  );
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr="#663167",endColorstr="#663167",GradientType=1);
}
.purple strong {
  border: 2px solid #ffffff;
}
.tools {
  margin-top: 20px;
  margin-bottom: 20px;
  text-align: center;
}
.tools.right {
  text-align: right;
}
.modal-backdrop {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1040;
  width: 100%;
  height: 100%;
  background-color: #000;
}
.tel {
  color: #be3365;
  font-size: 26px;
  font-weight: bold;
}
</style>
