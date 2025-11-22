∇Capsule[Collective_Rage_Grace_Dynamics_v0.1] : {

    // 1. 主轴：正负极端期望形成对称结构
    axes : {
        P1 : grace_expectation,     // 群体的“恩”期望（过度正向投射）
        P2 : resentment_load,       // 群体的“仇”负载（负向未满足）
        P3 : role_projection,       // 群体对目标的角色投射（英雄/反派）
        P4 : moral_axis,            // 道德二元化主轴
        P5 : narrative_memory        // 叙事记忆的滞后性
    },

    // 2. 群体版“大恩如大仇”的核心公式
    core_equation : {
        // 恩越大 → 期望越不可满足 → 崩落后的“仇”越剧烈
        E1 : grace_expectation↑ ↑ ⇒ resentment_load↑ ↑,  
        
        // 期望崩塌的瞬间形成“叙事翻转点”
        E2 : (grace_expectation - reality_gap) > threshold  
              ⇒ narrative_flip,

        // 正负极端共享同一“心理能量来源”
        E3 : P1 ⊕ P2 = same_energy_source,
        
        // 滞后记忆导致仇恨持续时间远大于恩惠半衰期
        E4 : narrative_memory_decay(grace) << narrative_memory_decay(grudge)
    },

    // 3. 动力层：群体如何从“恩”相变到“仇”
    phase_dynamics : {

        // 3.1 正向爆点
        phase_grace : {
            conditions : (P1.high ∧ P3.hero_role),
            features   : {
                f1 : mass_overidealization,
                f2 : group_sync_positive,
                f3 : defense_of_hero_archetype
            }
        },

        // 3.2 结构脆弱区：恩崩塌的临界点
        fragile_zone : {
            trigger : P1↑ ∧ (reality_gap↑),
            band    : high_sensitivity_band,
            outcome : {
                o1 : moral_axis_inversion,
                o2 : attention_gradient_collapse,
                o3 : conflict_axis_reversal
            }
        },

        // 3.3 负向爆点：恩→仇 的相变
        phase_resentment : {
            entry_condition : fragile_zone.trigger,
            features : {
                f1 : high_valence_flip,     // 情绪从正转负的“跃迁”
                f2 : narrative_darkening,   // 叙事结构变成指控型
                f3 : collective_mode_M2,    // 启动怒火模式
                f4 : memory_lock_in         // 仇恨锁定，难以逆转
            }
        }
    },

    // 4. 群体心智模式（调用社会场胶囊的节点）
    collective_modes_link : {
        positive_mode : {
            match : M6.heroism_mode,
            emergent : {
                e1 : expectation_overfit,
                e2 : emotional_resonance,
                e3 : crowd_identification
            }
        },
        negative_mode : {
            match : M2.rage_mode,
            emergent : {
                e1 : scapegoat_projection,
                e2 : moral_purification_logic,
                e3 : collective_punishment_drive
            }
        }
    },

    // 5. 级联链（cascade path）：群体如何形成“大恩如大仇”
    cascade_path : {

        path_grace_to_grudge : [
            (1) idealization_spike,
            (2) role_projection_lock,
            (3) expectation_saturation,
            (4) contradiction_exposure,
            (5) narrative_flip_point,
            (6) blame_assignment,
            (7) resentment_lock_in
        ],

        // 与自然灾害级联类似：从微扰到系统级事件
        system_level_outcome : {
            S1 : public_avatar_destroy,   // “毁偶像”，把目标从神坛扔下
            S2 : group_punitive_mode,     // 群体进入惩罚性集体行动
            S3 : memory_freeze,           // 群体形成长期敌意记忆
            S4 : competing_narratives_arm, // 反向叙事武装化
        }
    },

    // 6. 结构洞察（由舆情监测AI自然得到）
    emergent_insight : {
        X1 : grace_and_grudge = two_faces_of_same_group_energy,
        X2 : high_expectation_zone = inherently_unstable_phase,
        X3 : collective_flip = physical_phase_transition_analog,
        X4 : individual.big恩如大仇  ⊂  collective.big恩如大仇,
        X5 : group_memory_bias = grudge_retention >> grace_retention
    },

    output : ∇(P1 ⊕ P2 ⊕ P3 ⊕ P4 ⊕ P5) ↦ collective_grace_grudge_dynamics
}
