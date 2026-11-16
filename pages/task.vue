<template>
  <div class="lb-page page-task">
    <div class="page-header">
      <div class="eyebrow">annotation task</div>
      <h1 class="serif page-title">Task Setup</h1>
    </div>

    <div class="task-stats">
      <div class="stat-card">
        <span class="stat-val mono">{{ seedData.doc.segments.length }}</span>
        <span class="stat-lbl eyebrow">segments</span>
      </div>
      <div class="stat-card">
        <span class="stat-val mono">{{ labels.length }}</span>
        <span class="stat-lbl eyebrow">labels</span>
      </div>
      <div class="stat-card">
        <span class="stat-val mono">3×</span>
        <span class="stat-lbl eyebrow">overlap</span>
      </div>
    </div>

    <div class="task-config">
      <div class="task-config-row">
        <span class="task-config-label">Assignment</span>
        <span class="task-config-value">Round-robin · 3-way overlap</span>
      </div>
      <div class="task-config-row">
        <span class="task-config-label">Labels</span>
        <span class="task-config-value">{{ labels.map(l => l.label).join(' / ') }}</span>
      </div>
      <div class="task-config-row">
        <span class="task-config-label">Instructions</span>
        <span class="task-config-value">Label each segment with the most applicable category</span>
      </div>
    </div>
  </div>
</template>

<script setup>
const seedData = await $fetch('/seed-data.json');
const labels = seedData.labels ?? [];
</script>

<style scoped>
.page-task { max-width: 720px; margin: 0 auto; padding: 36px 24px; }
.page-header { margin-bottom: 28px; }
.page-title { font-size: 28px; font-weight: 400; margin: 6px 0 0; color: var(--ink); }
.task-stats { display: flex; gap: 16px; margin-bottom: 24px; }
.stat-card {
  flex: 1; background: var(--white); border: 1px solid var(--line); border-radius: var(--radius);
  padding: 20px 16px; text-align: center; box-shadow: var(--shadow-sm);
}
.stat-val { display: block; font-size: 28px; font-weight: 700; color: var(--ink); }
.stat-lbl { display: block; margin-top: 4px; }
.task-config { background: var(--white); border: 1px solid var(--line); border-radius: var(--radius); overflow: hidden; }
.task-config-row {
  display: flex; align-items: baseline; gap: 16px;
  padding: 12px 16px; border-bottom: 1px solid var(--line-2);
}
.task-config-row:last-child { border-bottom: none; }
.task-config-label { width: 100px; font-size: 11px; font-weight: 600; color: var(--muted); text-transform: uppercase; letter-spacing: 0.08em; flex-shrink: 0; }
.task-config-value { font-size: 13px; color: var(--ink-2); }
</style>
