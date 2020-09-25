<template>
  <Page v-if="data">
    <ActionButton />

    <Header v-bind="data.info" />

    <Section title="Career Summary" v-if="data.careerSummary">
      <p>{{ data.careerSummary }}</p>
    </Section>

    <Section title="Employment History" v-if="data.workExperiences">
      <Work
        v-for="work in data.workExperiences"
        :key="work.title"
        v-bind="work"
      />
    </Section>

    <Section title="Technical Skills" v-if="data.skills">
      <GenericList :items="data.skills" />
    </Section>

    <Section title="Education" v-if="data.schools">
      <School
        v-for="school in data.schools"
        :key="school.course"
        v-bind="school"
      />
    </Section>

    <Section title="Certificates" v-if="data.certificates">
      <Certificate
        v-for="certificate in data.certificates"
        :key="certificate.url"
        v-bind="certificate"
      />
    </Section>

    <Footer :info="data.lastUpdate" />
  </Page>
</template>

<script>
import Page from "@/components/Page.vue";
import Section from "@/components/Section.vue";
import GenericList from "@/components/GenericList.vue";
import Header from "@/components/Header.vue";
import Work from "@/components/Work.vue";
import School from "@/components/School.vue";
import Certificate from "@/components/Certificate.vue";
import Footer from "@/components/Footer.vue";
import ActionButton from "@/components/ActionButton.vue";

export default {
  name: "App",
  components: {
    Page,
    Section,
    GenericList,
    Header,
    Work,
    School,
    Certificate,
    Footer,
    ActionButton,
  },
  data() {
    return {
      data: null,
    };
  },
  beforeMount() {
    fetch("data.json")
      .then((res) => res.json())
      .then((res) => (this.data = res));
  },
};
</script>

<style>
@import url("./assets/app.css");
@import url("./assets/responsive.css");
@import url("./assets/animation.css");
@import url("./assets/print.css");
</style>