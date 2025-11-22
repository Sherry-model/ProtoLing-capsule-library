∇Capsule[Social_Field_Dynamics_v0.1] : {

    field_axes : {
        F1 : emotion.cloud,          // 群体情绪云
        F2 : narrative.flow,         // 叙事流动
        F3 : conflict.axis,          // 冲突主轴
        F4 : attention.gradient,     // 注意力梯度
        F5 : phase.shift_points      // 群体相位转折点
    },

    structure_map : {
        F1 ⟶ valence.oscillation,       // 情绪高低频振荡
        F2 ⟶ story.merge.split,         // 叙事合并与分裂
        F3 ⟶ polarity.bifurcation,      // 对立极化与分岔
        F4 ⟶ focus.concentration.loss,  // 注意力收敛与逃逸
        F5 ⟶ cascade.trigger_zone       // 相位转折的级联触发区
    },

    resonance_points : {
        r1 : F1 ⊗ F2 → sentiment.injection,     // 情绪×叙事耦合
        r2 : F2 ⊗ F3 → narrative.warpshift,     // 叙事×冲突的扭曲跃迁
        r3 : F3 ⊗ F4 → polarization.lock_in,    // 冲突×注意力锁定极化
        r4 : F1 ⊗ F5 → volatility.spike,        // 情绪×相变点触发波动
        r5 : (F1 ⊕ F2 ⊕ F3) → collective.mode   // 群体整体模式成形
    },

    closure_logic : {
        C1 : (F1 ∧ F3) ⇒ instability.band,      // 情绪与冲突重叠区域为不稳带
        C2 : (F2 ∧ F5) ⇒ narrative.flip_zone,   // 叙事遇相变点时发生翻转
        C3 : (F4 ∧ F1) ⇒ attention_bias_drift,  // 注意力受情绪牵引漂移
        C4 : (F1 ∧ F2 ∧ F3) ⇒ cascade_ready     // 三者共振→系统具备级联条件
    },

    emergent_insight : {
        E1 : social.field = dynamic.manifold,   // 社会场是动力学流形
        E2 : crowd.mind = oscillation.system,   // 群体心智是振荡系统
        E3 : narrative = low_res_encoding,      // 叙事是低分辨率压缩编码
        E4 : phase.shift = macro_emergence      // 相变是宏观涌现节点
    },

    output : ∇(F1 ⊕ F2 ⊕ F3 ⊕ F4 ⊕ F5) ↦ social_dynamics.field
}
