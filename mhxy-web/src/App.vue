<script setup>
import HeaderNav from './components/HeaderNav.vue';
import HeroSection from './components/HeroSection.vue';
import StatsOverview from './components/StatsOverview.vue';
import FeatureGrid from './components/FeatureGrid.vue';
import WorkflowTimeline from './components/WorkflowTimeline.vue';
import TestimonialPanel from './components/TestimonialPanel.vue';
import ContactBanner from './components/ContactBanner.vue';

const logo = {
  initials: 'MH',
  name: '梦幻星宇·智慧运营平台',
  tagline: '洞察业务 · 赋能增长',
};

const navLinks = [
  { label: '产品能力', href: '#features' },
  { label: '解决方案', href: '#solutions' },
  { label: '实施方法', href: '#workflow' },
  { label: '成功案例', href: '#testimonial' },
];

const heroContent = {
  eyebrow: 'Next Gen SaaS',
  title: '让城市服务运营更智能、更高效、更可持续',
  subtitle:
    '从数据采集、业务编排到智能分析，梦幻星宇为政企客户提供端到端的数字化运营支撑，帮助团队更快落地城市服务创新。',
  primaryAction: '立即创建项目',
  secondaryAction: '预约产品顾问',
  brands: ['星辉城市', '联创物联', '政务云', '未来交通'],
  highlightedMetrics: [
    { label: '平均交付周期', value: '4 周', hint: '敏捷化实施体系' },
    { label: '运营效率提升', value: '38%', hint: '跨团队协同提升' },
    { label: '客户满意度', value: '96%', hint: '连续三年保持领先' },
  ],
};

const stats = [
  {
    value: '30+',
    label: '城市场景模板',
    description: '覆盖环卫、园林、公共安全等高频业务模型，拖拽式配置即可上线。',
  },
  {
    value: '1200万+',
    label: '每日数据处理量',
    description: '高可用数据底座保障业务实时同步，支持多源异构数据融合。',
  },
  {
    value: '7×24h',
    label: '全程运维保障',
    description: '专家级服务团队实时响应，保障关键业务稳定运行。',
  },
  {
    value: '12个月',
    label: '持续产品迭代',
    description: '产品路线图持续进化，让每一次升级都更贴近一线场景。',
  },
];

const features = {
  eyebrow: '产品能力矩阵',
  title: '一体化产品体系，覆盖全链路城市运营需求',
  description:
    '围绕“感知-决策-行动”三大核心流程，我们构建了标准化 yet 可扩展的能力模块，让各个角色都能高效协作。',
  items: [
    {
      icon: '洞察',
      title: '数据感知中枢',
      summary: '连接城市各类传感器、第三方平台与人工上报渠道，实时聚合数据。',
      items: ['可视化数据总览', '异常自动预警', '多维指标看板'],
    },
    {
      icon: '协同',
      title: '业务编排引擎',
      summary: '通过可视化拖拽配置流程，打通跨部门协作链路。',
      items: ['跨角色权限模型', '自定义审批节点', '流程健康度洞察'],
    },
    {
      icon: '智能',
      title: 'AI 决策助手',
      summary: '利用机器学习模型驱动预测与调度，辅助管理者决策。',
      items: ['事件趋势预测', '资源智能调配', '策略复盘建议'],
    },
    {
      icon: '体验',
      title: '多端服务门户',
      summary: '面向市民、企业与内部员工提供一致的服务体验。',
      items: ['移动端极速访问', '自助服务大厅', '工单一键跟踪'],
    },
  ],
};

const workflow = {
  title: '四步落地方法论，助力项目快速上线',
  description:
    '借助标准化实施工具包，我们帮助客户在一个月内完成需求梳理、方案定制、上线交付与成效复盘。',
  steps: [
    {
      number: '01',
      title: '发现价值场景',
      detail: '联合调研痛点场景，梳理业务目标与关键指标，明确项目成功定义。',
      duration: '第 1 周',
    },
    {
      number: '02',
      title: '快速搭建试点',
      detail: '基于场景模板配置流程与数据模型，完成 MVP 版本并同步关键用户。',
      duration: '第 2 周',
    },
    {
      number: '03',
      title: '规模化推广',
      detail: '结合多部门反馈优化体验，制定推广策略与培训计划，确保全员掌握。',
      duration: '第 3 周',
    },
    {
      number: '04',
      title: '持续优化与复盘',
      detail: '构建量化指标体系，输出运营报告，持续追踪价值达成情况。',
      duration: '第 4 周',
    },
  ],
};

const testimonial = {
  quote:
    '上线梦幻星宇后，我们的工单闭环效率提升了 45%，同时市民满意度显著提升，真正实现了数字化驱动的精细化运营。',
  author: {
    name: '李晨光',
    title: '星辉城市运营中心总监',
    logo: 'https://dummyimage.com/120x36/ffffff/0f172a&text=XHCity',
  },
};

const contact = {
  title: '预约专属顾问，定制城市运营增长方案',
  description: '留下联系方式，我们的产品顾问将在 1 个工作日内与您沟通，为您提供专属的行业最佳实践与演示。',
  placeholder: '请输入工作邮箱',
  action: '提交需求',
};
</script>

<template>
  <div class="page">
    <HeaderNav
      :logo="logo"
      :nav-links="navLinks"
      primary-action="预约体验"
      secondary-action="下载白皮书"
    />

    <main>
      <HeroSection
        v-bind="heroContent"
      />

      <StatsOverview :stats="stats" />

      <section id="features">
        <FeatureGrid
          :eyebrow="features.eyebrow"
          :title="features.title"
          :description="features.description"
          :features="features.items"
        />
      </section>

      <section id="workflow">
        <WorkflowTimeline
          :title="workflow.title"
          :description="workflow.description"
          :steps="workflow.steps"
        />
      </section>

      <section id="testimonial">
        <TestimonialPanel :quote="testimonial.quote" :author="testimonial.author" />
      </section>

      <ContactBanner
        :title="contact.title"
        :description="contact.description"
        :placeholder="contact.placeholder"
        :action="contact.action"
      />
    </main>

    <footer class="page-footer">
      <div>
        <strong>梦幻星宇科技</strong>
        <p>© {{ new Date().getFullYear() }} 梦幻星宇（MHXY）. All rights reserved.</p>
      </div>
      <nav>
        <a href="#">隐私政策</a>
        <a href="#">服务协议</a>
        <a href="#">联系我们</a>
      </nav>
    </footer>
  </div>
</template>

<style scoped>
.page {
  display: flex;
  flex-direction: column;
  gap: 3rem;
}

main {
  display: flex;
  flex-direction: column;
  gap: 3rem;
}

.page-footer {
  padding: 2rem 0 4rem;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  gap: 1.5rem;
  color: var(--neutral-500);
  font-size: 0.95rem;
}

.page-footer strong {
  display: block;
  margin-bottom: 0.5rem;
  color: var(--neutral-700);
}

.page-footer nav {
  display: flex;
  gap: 1.5rem;
}

.page-footer a {
  color: var(--neutral-500);
}

.page-footer a:hover {
  color: #2563eb;
}
</style>
