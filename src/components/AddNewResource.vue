<template>
  <CardWrapper>
    <form class="form-container" @submit.prevent>
      <div>
        <label for="title">Title</label>
        <input type="text" name="title" id="title" ref="titleInputRef">
      </div>
      <div>
        <label for="description">Description</label>
        <textarea name="description" id="decription" rows="3" ref="descriptionInputRef"></textarea>
      </div>
      <div>
        <label for="link">Link</label>
        <input type="text" name="link" id="link" ref="linkInputRef">
      </div>
      <div class="input-error" v-if="inputError">
        <p>
          Please fill all input fields!
        </p>
      </div>
      <div class="button-group">
        <CustomButton class="save-button" @click="handleSave">SAVE RESOURCE</CustomButton>
      </div>
    </form>
  </CardWrapper>
</template>

<script>
import CardWrapper from './UI/CardWrapper.vue';
import CustomButton from './UI/CustomButton.vue';
export default {
  props: {},
  inject: ['addNewResourceToList'],
  data() {
    return { inputError: false };
  },
  methods: {
    handleSave() {
      const { titleInputRef, descriptionInputRef, linkInputRef } = this.$refs;
      const { handleError, isEmptyInput, addNewResourceToList } = this;

      const titleValue = titleInputRef.value;
      const descriptionValue = descriptionInputRef.value;
      const linkValue = linkInputRef.value;

      handleError(titleInputRef, descriptionInputRef, linkInputRef);

      if (!isEmptyInput(titleValue) && !isEmptyInput(descriptionValue) && !isEmptyInput(linkValue)) {
        this.inputError = false;
        addNewResourceToList(titleValue, descriptionValue, linkValue);
      } else {
        this.inputError = true;
      }
    },
    handleError() {
      [...arguments].forEach(ref => {
        ref.classList.remove("invalid-input");
        if (ref.value.trim() === '') {
          ref.classList.add("invalid-input");
        }
      });
    },
    isEmptyInput(value) {
      return value.trim() === '';
    }
  },
  components: { CardWrapper, CustomButton }
}
</script>

<style scoped>
.form-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

div {
  display: flex;
  flex-direction: column;
  width: 100%;
  margin-bottom: 1.5rem;
}

label {
  font-weight: 700;
  margin-bottom: 2px
}

.button-group {
  flex-direction: row;
  justify-content: flex-end;
  margin-bottom: 0;
}

.save-button {
  width: 200px
}

.input-error {
  color: salmon;
}

.invalid-input {
  border: 1px solid salmon;
}
</style>