∇Capsule[GraceGrudge_FoldingMap_v0.1] : {

    // 0. 引用两枚已有胶囊的轴（抽象引用，不展开原文）
    individual_axes : {
        iE : self.grace_load,        // 个体“恩”负载（高度理想化 & 感恩绑定）
        iR : self.grudge_load,       // 个体“仇”负载（被辜负/被背叛感）
        iP : self.other_projection,  // 个体对他人的角色投射（救世主/加害者）
        iM : moral_split,            // 内部道德二元化（非黑即白）
        iN : personal_narrative      // 个人叙事记忆弧线
    },

    collective_axes : {
        cE : P1.grace_expectation,   // 群体的“恩”期望场
        cR : P2.resentment_load,     // 群体的“仇”负载场
        cP : P3.role_projection,     // 群体的角色投射（英雄/反派）
        cM : P4.moral_axis,          // 群体道德主轴（正义/邪恶）
        cN : P5.narrative_memory     // 群体叙事记忆 & 舆论史
    },

    // 1. 折叠方向一：个体 → 群体（many-to-field）
    fold_up : {

        // 1.1 多个个体大恩如大仇的“投射叠加”为群体场
        F1 : Σ(iE over agents) ↦ cE,    // 众多个体的恩期望 叠加 → 群体恩场
        F2 : Σ(iR over agents) ↦ cR,    // 众多个体的怨恨 叠加 → 群体仇场

        // 1.2 个体角色投射在公共叙事中对齐为“英雄/恶人”原型
        F3 : cluster(iP) ↦ cP.archetype_set, 
             // 多个不同“他在我心中是什么”的投射 → 公共符号中的英雄/恶人模板

        // 1.3 个体道德二元化在群体中对齐为道德轴（正义 vs 败类）
        F4 : normalize(iM over crowd) ↦ cM.binary_axis,

        // 1.4 个体故事被选入或排除于公共叙事（媒体/社交平台筛选）
        F5 : filter(iN) via attention/visibility ↦ cN.dominant_arc
    },

    // 2. 折叠方向二：群体 → 个体（field-to-mind 回流）
    fold_down : {

        // 2.1 群体“恩场”反向强化个体对目标的理想化
        G1 : cE.high_density ↦ iE↑ for aligned_agents,
             // “大家都觉得他是恩人” → 个体更加不敢质疑

        // 2.2 群体“仇场”反向塑造个体的敌意体验
        G2 : cR.lock_in ↦ iR.stable, 
             // 群体已认定“他是坏的” → 个体很难再调和自己的复杂情感

        // 2.3 群体英雄/恶人原型压扁个体复杂认知
        G3 : cP.hero/villain_template ↦ iP.quantization,
             // 复杂人变成“只能选英雄或恶人”的两格选项

        // 2.4 群体道德主轴约束个体的表达空间
        G4 : cM.sharpened_axis ⇒
                (iM.forced_alignment ∨ silence),
             // 道德轴越尖锐 → 个体越被迫选边站/闭嘴

        // 2.5 群体叙事记忆覆盖个体真实记忆
        G5 : cN.dominant_arc ↦ override(iN.subtle_details),
             // 细腻的个人记忆被“官方/主流故事”粗暴覆盖
    },

    // 3. 叙事翻转（英雄 → 恶人）的相变折叠
    narrative_flip_fold : {

        // 3.1 微观层：你说的“一串小事叠加酝酿”
        micro_accumulation : {
            m1 : small_inconsistencies,      // 小的不一致
            m2 : unmet_promises,             // 小的没做到
            m3 : value_discrepancies,        // 价值观细微偏差
            m4 : rumor/noise_injection       // 噪音、谣言、模糊证据
        },

        // 3.2 在个体心理中的表现
        individual_effect : {
            H1 : m1..m4 → iE.decay + iR.seed,
            // 原本纯“恩”中混入细小“砂砾”，恩场开始退潮，怨种开始发芽
            H2 : cognitive_dissonance↑ ⇒ iM.stress, 
            H3 : self_story(“我是不是看错人了？”) 启动
        },

        // 3.3 在群体场中的表现
        collective_effect : {
            K1 : synchronized(m1..m4 reports) ↦ cE.surface_cracks,
            K2 : \# of dissonant_stories↑  ↦ cN.alt_arc.gain_strength,
            K3 : cM.shifts_from(“不容质疑的好人”) → (“可能有问题的人”),
            K4 : fragile_zone_entered if (cE.high ∧ reality_gap↑)
        },

        // 3.4 触发宏观相变：英雄 → 恶人
        macro_flip : {
            trigger_event : T*,  // 一个大的突发事件（丑闻爆出、重大失误、被重新解读的旧事）
            condition     : (fragile_zone_entered ∧ T* ≠ 必须极端),
            result : {
                R1 : cP.hero → villain,                  // 角色原型翻转
                R2 : cN.rewrite(“他一直都是这样的”),    // 叙事回溯性重写
                R3 : cR.surge,                           // 仇负载激增
                R4 : crowd_mode → rage_mode (M2),        // 群体进入怒火模式
                R5 : iE → iR for many agents (grace → grudge)
            }
        }
    },

    // 4. 结构同构：个体 vs 群体“大恩如大仇”是同一动力学在不同尺度的投影
    isomorphism : {
        iso_1 : iE ↔ cE on different scales,        // 个体期望 vs 群体期望场
        iso_2 : iR ↔ cR (情感负载的聚合),
        iso_3 : iP ↔ cP (角色投射 vs 公共符号),
        iso_4 : iM ↔ cM (内在二元化 vs 公共道德二元化),
        iso_5 : iN ↔ cN (个人叙事 vs 集体叙事史),

        // 关键：相变结构同构
        iso_phase : individual_flip_struct ≈ collective_flip_struct,
        comment   : "micro心理临界 → macro叙事临界，动力形式相同，只是承载体不同"
    },

    output : fold( individual_axes, collective_axes ) 
             ↦ { hero→villain_narrative_flip, 
                  grace→grudge_field_transition }
}
