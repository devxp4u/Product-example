<script setup>
import { useProjects } from '@/composables/useProjects';

const { isModalOpen, openModal, closeModal, Modal } = useProjects()
</script>

<template>
  <main class="px-10 py-6 max-w-[1200px] w-full mx-auto">
    <!-- Page header -->
    <div class="flex items-center justify-between mb-8">
      <h1 class="text-on-surface text-[1.5rem] font-headline font-bold leading-tight tracking-tight">
        Projects
        <span class="text-outline text-body-md font-normal ml-2 relative -top-1">(5)</span>
      </h1>
      <form @submit.prevent="openModal">
        <button
          class="primary-gradient-cta inline-flex items-center justify-center rounded-md h-10 px-4 text-on-primary text-body-md font-semibold shadow-sm hover:opacity-90 transition-opacity"
          type="submit"
        >
          <span class="material-symbols-outlined mr-2 text-[18px]">add</span>
          New Project
        </button>
      </form>
    </div>

    <!-- Filters -->
    <div class="flex gap-3 mb-8">
      <button class="px-4 py-1.5 rounded-sm bg-surface-container-highest text-on-surface text-body-md font-medium transition-colors">
        All
      </button>
      <button class="px-4 py-1.5 rounded-sm hover:bg-surface-container-low text-on-surface-variant hover:text-on-surface text-body-md font-medium transition-colors">
        Active
      </button>
      <button class="px-4 py-1.5 rounded-sm hover:bg-surface-container-low text-on-surface-variant hover:text-on-surface text-body-md font-medium transition-colors">
        In Progress
      </button>
      <button class="px-4 py-1.5 rounded-sm hover:bg-surface-container-low text-on-surface-variant hover:text-on-surface text-body-md font-medium transition-colors">
        Archived
      </button>
    </div>

    <!-- Project List -->
    <div class="flex flex-col gap-6">
      <div
        v-for="item in [1, 2, 3]"
        :key="item"
        class="bg-surface-container-lowest rounded-md p-6 hover:bg-surface-container-low transition-colors group"
        style="box-shadow: 0 4px 20px rgba(19, 27, 46, 0.03)"
      >
        <div class="flex justify-between items-start">
          <div class="flex-1">
            <div class="flex items-center gap-3 mb-2">
              <h3 class="text-on-surface font-headline font-semibold text-[1.125rem]">
                Core Banking API v2
              </h3>
              <span class="inline-flex items-center px-2 py-0.5 rounded-sm text-label-sm font-medium bg-primary-fixed text-on-primary-fixed">
                Active
              </span>
            </div>
            <p class="text-on-surface-variant text-body-md max-w-2xl mb-4">
              Refactoring the main transaction processing engine to support microservices architecture and improved throughput.
            </p>
            <div class="flex items-center gap-6">
              <div class="flex items-center gap-1.5 text-on-surface-variant text-label-sm">
                <span class="material-symbols-outlined text-[16px]">schedule</span>
                Modified 2 hours ago
              </div>
              <div class="flex -space-x-2 overflow-hidden">
                <img
                  alt=""
                  class="inline-block h-6 w-6 rounded-full ring-2 ring-surface-container-lowest"
                  src="https://lh3.googleusercontent.com/aida-public/AB6AXuCRyMGbMZPyznirnH0ncsRMolkPbybctuaxqAeR3iu59EyfVAWC-4ALmI0cQhLQ97RZOQkON9JePxbMJ6FurbCIqmuw-G_9o-lFLOVYfq2UTAS4P6af7QXbtS8g5vJmuSEMYAYztO5F7ASP8-6-I4g_J6L2jvW4AD9Pmd0VXNwTLNRZYPUoks3E62pWO144ZQmWQP1-bLxr4Mu-NOhWYwIaZC7uztEZYEc509KXi9rCiJArYmN9PbJc0QZGiXCaJmLl0wCjB9-zhyOj"
                />
                <img
                  alt=""
                  class="inline-block h-6 w-6 rounded-full ring-2 ring-surface-container-lowest"
                  src="https://lh3.googleusercontent.com/aida-public/AB6AXuB2WT7ysa0XJEIXoRk1BvYCx1ZqvRwf23KviHVMFLVouh8v2b5ggqf2KLydNe3U678-2W4P07wAO_XKDrNh59TAHz8P5itCDX_IHr90iNGzbEhVZ3diiEZvh4K4N58bjdSp9c9vyUhiDQL7BhtU8NUmc1zpK_vSj5kJy9YT8YFu_0IUSej8OS0sIJJcKUqHtTVbFn8qoiVZjKNuS5oi1vB9KTv8eiikzmhOVFQB5PylVUqAO_9IByjzfYESx6lh_lNxysp7C2BeEYlc"
                />
                <img
                  alt=""
                  class="inline-block h-6 w-6 rounded-full ring-2 ring-surface-container-lowest"
                  src="https://lh3.googleusercontent.com/aida-public/AB6AXuCWoO3gQnIplCSp2eDnE84u_abkzGyVqq4x1cdme3ZkICXleFqmmWcxNvpWWLQ3HqbW1YaX9rjzORYejD9VC7mBl9Osd5L9mspHbXLHwpj5Zz4b8Xz1Mn9fk_50FtFC31Ls6goQOGSYzG0igN_M62t23k7FXYhEuncVgij_Wu7F1P5hmKRGVjy-R_F4v5EzQPQXUX7lUls6wLv2_ZixCkxY6bW_AfaAWMew8t7xoJVYs5pYCW14mO0SbpGLfXPbkkF7aARtI3DFsQRn"
                />
              </div>
            </div>
          </div>
          <div class="flex items-center gap-2">
            <button class="p-2 text-outline hover:text-primary transition-colors rounded-sm hover:bg-surface-container-high opacity-0 group-hover:opacity-100">
              <span class="material-symbols-outlined">edit</span>
            </button>
            <button class="p-2 text-outline hover:text-on-surface transition-colors rounded-sm hover:bg-surface-container-high">
              <span class="material-symbols-outlined">more_vert</span>
            </button>
          </div>
        </div>
      </div>
    </div>

    <Modal v-if="isModalOpen" @close="closeModal" />
  </main>
</template>

<style>
.primary-gradient-cta {
  background: linear-gradient(135deg, #3525cd 0%, #4f46e5 100%);
}
</style>
