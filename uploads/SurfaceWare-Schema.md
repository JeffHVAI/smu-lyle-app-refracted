{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "title": "SurfaceWareSpatialLayoutSchema",
  "version": "0.2-alpha",
  "meta": {
    "schema_version": "0.2-alpha",
    "generated_by": "Refract_Engine_v2.5",
    "target_platform": "Hover OS / SurfaceWare Runtime",
    "ingestion_instructions": "AI Design Agents: Convert 2D Cartesian layout trees into this relational anthropometric schema. Enforce target minimums and layout padding stringently."
  },
  "scene_calibration": {
    "display_type": "wall_projection_4k",
    "sensor_position": "top_center",
    "expected_user_posture": "standing",
    "optimal_interaction_distance": "1.5m",
    "shadow_suppression": {
      "enabled": true,
      "shadow_filtering_level": "high",
      "body_occlusion_rejection_confidence": 0.88
    },
    "environmental_cues": {
      "floor_anchor_indicator": true,
      "hand_entry_zone_visible": true,
      "standing_sweet_spot_meters": 1.5
    }
  },
  "human_factors_config": {
    "ttu_research_version": "2026.2",
    "parallax_compensation": "dynamic",
    "comfort_zone_bias": "center_mass",
    "cross_body_penalty": 0.20,
    "gorilla_arm_mitigation": {
      "max_elevation_angle_deg": 35,
      "preferred_y_range": ["waist", "chest"]
    }
  },
  "layout_zones": [
    {
      "id": "primary_interaction_zone",
      "description": "The Green Zone: Minimal arm strain, waist-to-chest elevation, high gesture accuracy.",
      "anchor": "user_torso_relative",
      "y_range": ["waist", "chest"],
      "x_range": ["shoulder_width_plus_20"],
      "target_padding_px": 40
    },
    {
      "id": "display_only_zone",
      "description": "Areas too high, low, or far at extreme edges for comfortable interaction.",
      "allow_interactables": false,
      "content_type": ["hero_images", "brand_headers", "background_video"]
    }
  ],
  "components": [
    {
      "id": "product_card_01",
      "type": "smart_card",
      "content": {
        "title": "2026 Model X",
        "price": "$45,000",
        "image_url": "assets/img_01.png"
      },
      "surface_physics": {
        "magnetism_strength": 0.95,
        "magnetic_snap_radius_px": 25,
        "friction": 0.2,
        "z_depth_active": 50,
        "dwell_trigger_ms": 350
      },
      "ergonomic_placement": {
        "target_zone": "primary_interaction_zone",
        "priority": "high",
        "min_target_size_px": {
          "width": 80,
          "height": 80
        },
        "visual_offset": {
          "x": 0,
          "y": "-50px",
          "note": "Lowered visually to align with hand perception vs eye angle (Parallax Gap)."
        }
      }
    }
  ]
}