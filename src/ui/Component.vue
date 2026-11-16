<template>
  <div class="tb-shell">
    <div class="tb-header">
      <span class="tb-eyebrow">annotation task</span>
      <h3 class="tb-title">Task Builder</h3>
    </div>

    <div class="tb-summary">
      <div class="tb-stat">
        <span class="tb-stat-val">{{ config.docs }}</span>
        <span class="tb-stat-lbl">documents</span>
      </div>
      <div class="tb-stat">
        <span class="tb-stat-val">{{ config.overlap }}×</span>
        <span class="tb-stat-lbl">annotator overlap</span>
      </div>
      <div class="tb-stat">
        <span class="tb-stat-val">{{ config.segments }}</span>
        <span class="tb-stat-lbl">segments</span>
      </div>
    </div>

    <div class="tb-config">
      <div class="tb-config-row">
        <span class="tb-config-label">Labelset</span>
        <span class="tb-config-value">Standard_Legal_Span_v1 · 4 labels</span>
      </div>
      <div class="tb-config-row">
        <span class="tb-config-label">Assignment</span>
        <span class="tb-config-value">Round-robin · 3-way overlap</span>
      </div>
      <div class="tb-config-row">
        <span class="tb-config-label">Instructions</span>
        <span class="tb-config-value">Label each segment with the most applicable category</span>
      </div>
    </div>
  </div>
</template>

<script setup>
const config = { docs: 247, overlap: 3, segments: 3418 };
</script>

<style scoped>
.tb-shell { font-family: system-ui, sans-serif; padding: 20px; display: flex; flex-direction: column; gap: 20px; }
.tb-eyebrow { font-family: monospace; font-size: 10px; font-weight: 500; letter-spacing: 0.14em; text-transform: uppercase; color: #8C8579; display: block; }
.tb-title { font-size: 20px; font-weight: 600; margin: 4px 0 0; color: #1A1714; }

.tb-summary { display: flex; gap: 12px; }
.tb-stat {
  flex: 1; background: #fff; border: 1px solid #E5DFD3; border-radius: 10px;
  padding: 16px; text-align: center;
}
.tb-stat-val { display: block; font-size: 26px; font-weight: 700; font-family: monospace; color: #1A1714; }
.tb-stat-lbl { display: block; font-size: 10px; text-transform: uppercase; letter-spacing: 0.10em; color: #8C8579; margin-top: 4px; }

.tb-config { background: #fff; border: 1px solid #E5DFD3; border-radius: 10px; overflow: hidden; }
.tb-config-row {
  display: flex; align-items: baseline; gap: 16px;
  padding: 12px 16px; border-bottom: 1px solid #F4F0E6;
}
.tb-config-row:last-child { border-bottom: none; }
.tb-config-label { width: 100px; font-size: 11px; font-weight: 600; color: #8C8579; text-transform: uppercase; letter-spacing: 0.08em; flex-shrink: 0; }
.tb-config-value { font-size: 13px; color: #4A453E; }
</style>
