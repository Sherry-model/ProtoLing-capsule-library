∇Capsule[Avoidance_Window_v0.1] : {

    preconditions : {
        C1 : early_self_initialized,
        C2 : narrative_noise_low,
        C3 : no_role_overload
    },

    window_properties : {
        W1 : short_duration,
        W2 : high_fragility,
        W3 : structure_growth >> narrative_capacity
    },

    allowed_actions : {
        A1 : build_narrative_buffer,
        A2 : avoid_role_projection,
        A3 : maintain_structure_distance_internal
    },

    failure_conditions : {
        F1 : projection_surge,
        F2 : political_activation,
        F3 : early_self_overexposed
    }
}
