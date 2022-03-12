<script setup>
import "floating-vue/dist/style.css";

const handleMouseOver = ({ target }) => {
  if (target.classList.contains("v-popper--has-tooltip")) {
    target.classList.add("v-popper--is-hovered");
    if (
      target.classList.contains("property") ||
      target.classList.contains("value")
    ) {
      target.parentElement.classList.add("v-popper--is-hovered");
    }
    target.addEventListener("mouseleave", handleMouseLeave);
  }
};

const handleMouseLeave = ({ target }) => {
  if (target.classList.contains("v-popper--has-tooltip")) {
    target.classList.remove("v-popper--is-hovered");
    if (
      target.classList.contains("property") ||
      target.classList.contains("value")
    ) {
      target.parentElement.classList.remove("v-popper--is-hovered");
    }
    target.removeEventListener("mouseleave", handleMouseLeave);
  }
};
</script>

<template>
  <div class="anatomy" @mouseover="handleMouseOver">
    <div class="selector" v-tooltip.left="'Selector'">
      <div class="class">.my-css-rule</div>
      <div class="bracket">&#123;</div>
    </div>
    <div class="declarations">
      <div class="declaration" v-tooltip.left="'Declaration'">
        <div class="property" v-tooltip="'Property'">background:</div>
        <div class="value" v-tooltip="'Value'">red;</div>
      </div>
      <div class="declaration" v-tooltip.left="'Declaration'">
        <div class="property" v-tooltip="'Property'">color:</div>
        <div class="value" v-tooltip="'Value'">blue;</div>
      </div>
      <div class="declaration" v-tooltip.left="'Declaration'">
        <div class="property" v-tooltip="'Property'">font-size:</div>
        <div class="value" v-tooltip="'Value'">1rem;</div>
      </div>
    </div>
    <div class="bracket">&#125;</div>
  </div>
</template>

<style scoped>
.selector {
  width: max-content;
  display: flex;
  color: #c38b25;
  cursor: pointer;
}
.selector .bracket {
  margin-left: 0.5rem;
}
.selector .class {
  pointer-events: none;
}
.bracket {
  color: #cfcf37;
}
.declaration {
  width: max-content;
  display: flex;
  margin: 0.5rem 0.5rem 0.5rem 1.5rem;
  cursor: pointer;
}
.declaration .property {
  position: relative;
  color: #ccc;
  cursor: pointer;
}
.declaration .value {
  margin-left: 0.75rem;
  color: #c38b25;
  cursor: pointer;
}
.selector .class,
.declaration,
.property,
.value {
  transition: all 0.2s ease;
}
.selector.v-popper--is-hovered .class {
  padding: 0.5rem;
  background-color: rgb(194, 15, 15);
}
.declaration.v-popper--is-hovered {
  padding: 0.5rem;
  background-color: rgb(106, 106, 114);
}
.property.v-popper--is-hovered {
  background-color: rgb(43, 172, 177);
}
.value.v-popper--is-hovered {
  background-color: rgb(129, 28, 168);
}
</style>
