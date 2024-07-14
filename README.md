# WorkoutML (Workout Markup Language)

WorkoutML is a structured scripting language designed to create comprehensive and customizable workout programs for fitness applications. This repository provides the official documentation, examples, and resources for using WorkoutML, making it easy for developers, trainers, and fitness enthusiasts to design, share, and implement effective workout routines.

## Introduction

WorkoutML allows users to define workout blocks, training profiles, and overall programs with a clear and consistent syntax. This documentation will help you understand how to use WorkoutML to build effective workout plans.

## Structure Overview

### Workout Block

A Workout Block consists of exercises grouped by specific training mechanisms. Each block can focus on different fitness goals such as strength, endurance, or hypertrophy.

Example:
```yaml
workout:
  - block: "Strength Training Block"
    description: "A block focusing on strength training"
    mechanisms:
      - name: "Hypertrophy"
        description: "Muscle growth phase"
        phases: ["Primary", "Assistant"]
        exercises:
          - name: "Squat"
            type: "PrimaryStrengthExercise"
            description: "A basic strength exercise for legs"
            tare: 45
            tare_description: "Empty barbell"
            load_units: "lbs"
            rating_system: "RPE Scale"
            volume: "High Volume"
            levels: [3]
            rep_units: "reps"
            phases: ["Primary"]

### Training Profiles
Training profiles define the structure of workout cycles, including the number of cycles, days per cycle, and intensity levels.

training_profiles:
  - num_cycles: 3
    days_per_cycle: 7
    level_i: 3
    level_f: 1
    block:
      block: "Strength Training Block"
      description: "A block focusing on strength training"

### Programs
Programs combine multiple training profiles to create a comprehensive fitness plan.

programs:
  - program: "Ultimate Fitness Program"
    details: "A comprehensive program for overall fitness"
    training_profiles:
      - start_cycle: 1
        start_day: 1
        profile:
          num_cycles: 3
          days_per_cycle: 7
          level_i: 3
          level_f: 1
          block:
            block: "Strength Training Block"
            description: "A block focusing on strength training"
      - start_cycle: 4
        start_day: 1
        profile:
          num_cycles: 2
          days_per_cycle: 5
          level_i: 2
          level_f: 0
          block:
            block: "Endurance Training Block"
            description: "A block focusing on endurance training"
