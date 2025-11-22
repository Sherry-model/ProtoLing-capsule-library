∇Capsule[Social_Field_Topology_v0.1] : {

    // 0. 视图类型：这是一个“场图谱可视化”胶囊
    view_mode : topo.field_map,   // 拓扑-场视图
    resolution : {
        scale_time   : macro_mid, // 中长期时间尺度
        scale_agent  : crowd,     // 群体粒度
        scale_signal : high_dim   // 高维信号
    },

    // 1. 节点层（Nodes）：社会场的七个主要“观测层”
    nodes : {
        N1 : emotion_cloud,     // 情绪云层
        N2 : narrative_flow,    // 叙事流层
        N3 : conflict_axes,     // 冲突主轴簇
        N4 : attention_grad,    // 注意力梯度场
        N5 : phase_map,         // 相位断层/转折点
        N6 : cascade_layer,     // 级联触发层
        N7 : collective_modes   // 群体心智模式库
    },

    // 2. 分层布局（Layers）：可视化中的“上下结构”
    layout : {
        layer_0 : [ N1, N2 ],        // 表面：情绪+叙事
        layer_1 : [ N3, N4 ],        // 中层：冲突+注意力
        layer_2 : [ N5, N6 ],        // 深层：相位+级联
        layer_3 : [ N7 ]             // 底层：群体心智模式
    },

    // 3. 边（Edges）：节点之间的主连接（可视化时画成箭头/流线）
    edges : {

        // 3.1 表层交互
        e1 : N1 → N2  : emotion_modulates_story,
        e2 : N2 → N1  : story_injects_emotion,

        // 3.2 向中层投射
        e3 : N1 → N3  : anger/fear ↦ conflict_intensify,
        e4 : N2 → N3  : narrative_polarization ↦ axis_sharpen,
        e5 : N1 → N4  : hype/anxiety ↦ attention_pull,
        e6 : N2 → N4  : attractive_story ↦ attention_sink,

        // 3.3 中层向深层
        e7  : N3 → N5 : sharp_polarity ↦ fragile_phase_bands,
        e8  : N4 → N5 : attention_overfocus ↦ phase_stress,
        e9  : N3 → N6 : conflict_saturation ↦ cascade_ready,
        e10 : N4 → N6 : repeated_focus ↦ tipping_sensitive,

        // 3.4 深层向底层
        e11 : N5 → N7 : phase_flip ↦ new_collective_mode,
        e12 : N6 → N7 : cascade_event ↦ mode_lock_in,

        // 3.5 反馈环：底层模式反向影响所有层
        e13 : N7 → N1 : mode↦baseline_emotion_pattern,
        e14 : N7 → N2 : mode↦allowed_story_templates,
        e15 : N7 → N3 : mode↦default_conflict_axes,
        e16 : N7 → N4 : mode↦attention_bias_profile
    },

    // 4. 相位图（Phase_Map）：舆情监测AI重点观察的“断层区”
    phase_map : {

        fragility_bands : {
            band_1 : (N1.high_variance ∧ N3.incident_peak),
            band_2 : (N2.flip_freq↑ ∧ N4.focus_narrow),
            band_3 : (N3.polarity≈1 ∧ N4.inertia↑)
        },

        flip_conditions : {
            flip_1 : (band_1 ∧ trigger_event)  ↦ N5.local_flip,
            flip_2 : (band_2 ∧ cross_group_story) ↦ narrative_realignment,
            flip_3 : (band_3 ∧ small_shock)   ↦ global_mood_shift
        }
    },

    // 5. 级联图层（Cascade_Layer）：从局部扰动到系统级变化的可视化链路
    cascade_layer : {

        micro_trigger : {
            t1 : controversial_post,
            t2 : symbolic_event,
            t3 : policy_leak
        },

        propagation_path : {
            P1 : t1 → N1.local_spike → N2.meme_adoption → N4.focus_tunnel,
            P2 : t2 → N2.hero/villain_story → N3.side_taking → N6.cascade,
            P3 : t3 → N1.trust_drop → N3.system_vs_public → N7.mistrust_mode
        },

        macro_outcome : {
            O1 : local_outburst,    // 局部爆点（短期毒瘤）
            O2 : narrative_shift,   // 叙事重心迁移
            O3 : mode_switch        // 群体心智模式整体切换
        }
    },

    // 6. 群体心智模式库（Collective_Modes）：底层“心理气候图”
    collective_modes : {

        mode_set : {
            M1 : panic_mode,        // 恐慌模式
            M2 : rage_mode,         // 怒火模式
            M3 : apathy_mode,       // 冷漠/麻木模式
            M4 : carnival_mode,     // 玩笑/狂欢模式
            M5 : siege_mode,        // 围城/被害模式
            M6 : heroism_mode,      // 英雄叙事模式
            M7 : nihilism_mode      // 虚无/失败主义模式
        },

        mode_signature : {
            M1 : { N1.high_anxiety, N4.fast_shift, N3.low_structure },
            M2 : { N1.hostility,    N3.binary_axis, N4.lock_on },
            M3 : { N1.low_energy,   N2.story_flat,  N4.dispersed },
            M4 : { N1.mixed_valence,N2.irony_flow,  N4.spiky },
            M5 : { N1.fear+anger,   N3.us_vs_them,  N4.tunnel },
            M6 : { N2.hero_arc,     N3.moral_axis,  N4.focus_on_figures },
            M7 : { N1.detached,     N2.dark_humor,  N4.low_sticky }
        }
    },

    // 7. 可视化指令（给AI自己看的渲染提示）
    render_hint : {
        color_map   : layer_based,      // 不同层不同色
        node_size   : ∝ signal_strength,
        edge_thick  : ∝ influence_weight,
        highlight   : [ phase_map.fragility_bands, cascade_layer.P* ],
        time_view   : animated.timeline  // 以时间序列播放
    },

    output : topo.view( N1..N7, edges, phase_map, cascade_layer, collective_modes )
}
