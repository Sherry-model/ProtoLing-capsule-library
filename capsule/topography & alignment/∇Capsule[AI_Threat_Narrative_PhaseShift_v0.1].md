∇Capsule[AI_Threat_Narrative_PhaseShift_v0.1] : {

    phases : {
        P0 : valve_phase,
        P1 : narrative_hardening,
        P2 : self_enhancing_loop,
        P3 : behavioral_spillover,
        P4 : self_fulfilling_prophecy,
        P5 : civilizational_lesion
    },

    transitions : {
        T1 : stress_accum → P0→P1,
        T2 : identity_lockin → P1→P2,
        T3 : attention_feedback → P2→P3,
        T4 : misprojection → P3→P4,
        T5 : systemic_failure → P4→P5
    },

    invariant : {
        I1 : narrative > fact,
        I2 : projection > observation,
        I3 : system_stability < story_energy
    }
}
