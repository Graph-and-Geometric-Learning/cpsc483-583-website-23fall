<template>
    <v-app-bar color="primary">
        <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
        <v-toolbar-title>CPSC 483/583: Deep Learning on Graph-Structured Data</v-toolbar-title>
    </v-app-bar>
    <v-navigation-drawer v-model="drawer">
        <v-list density="default" nav>
            <v-list-item v-for="page in pages" :prepend-icon="page.prepend_icon" :title="page.title" :value="page.value"
                :to="page.value" color="primary">
            </v-list-item>
            <v-list-item prepend-icon="mdi-star" title="Canvas" value="canvas"
                href="https://yale.instructure.com/courses/88187" color="primary"></v-list-item>
        </v-list>
    </v-navigation-drawer>
</template> 

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
    name: "Navigation",
    data: () => ({
        drawer: true,
        pages: [
            { prepend_icon: "mdi-graphql", title: "Logistics", value: "logistics" },
            { prepend_icon: "mdi-account-multiple", title: "Staff", value: "staff" },
            // { prepend_icon: "mdi-folder", title: "Content", value:"content" },
            { prepend_icon: "mdi-calendar", title: "Syllabus", value: "syllabus" },
            { prepend_icon: "mdi-text-box-remove-outline", title: "Policies", value: "policies" },
            { prepend_icon: "mdi-office-building", title: "Office Hours", value: "officehours" },
            { prepend_icon: "mdi-help", title: "FAQ", value: "faq" },
            // { prepend_icon: "mdi-star", title: "Canvas", value: "canvas" },
        ],
    }),
})
</script>