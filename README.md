Project Overview

This project explores the development of a VR-based spatial editing and visualisation environment using Unreal Engine 5, with a focus on:

VR interaction design

Editor-style object manipulation

Integration with Twinmotion for high-fidelity architectural visualisation

The long-term goal is to allow users to position, edit, and preview scene elements in VR, then export those layouts into Twinmotion for real-time rendering and presentation.

This repository represents the current state of development at the interim demo milestone.

Current Features (Implemented)
1. VR Pawn & Input System

Custom BP_VRPawn built on Unreal’s VR Template

Enhanced Input system configured with:

IMC_Hands

IA_Grab

Hand grip actions

PSVR2 / VR controller inputs verified via:

Print String debugging

SteamVR / Theater Mode testing

2. Hand Representation & Collision

Left and right hand skeletal meshes (HandMesh_L, HandMesh_R)

Per-hand grab collision spheres (GrabSphere_L, GrabSphere_R)

Grab spheres manually aligned to palm position

Collision channels configured for overlap-based interaction testing

3. Placeable Objects

BP_Placeable actor representing interactable scene objects

Components:

Static Mesh

Box Collision

Overlap detection implemented to track when a hand is within interaction range

4. Editor-Style Interaction Workflow (Demo-Safe)

Due to platform-specific input complexity, object interaction is primarily performed using PSVR2 controller feedback via SteamVR's Theater Mode.

This allows:

Reliable object selection

Transformation and placement

Consistent demonstration of the interaction pipeline

This workflow mirrors editor-style VR tools, where VR is used as a spatial interface rather than relying exclusively on physical grabbing.

5. Twinmotion "Pipelining"

Scene layout created in Unreal Engine

Assets and transforms prepared for export

Twinmotion VR viewing mode is used to observe raw environments and apply simple "textures" to objects, as well as teleportation for enhanced traversal,lighting/environment manipulation for varied insights


Current Limitations

The following issues are known and documented at this stage:

Physics-based VR grabbing is partially implemented but not production-stable

Grab logic works at the input and collision level, but:

Attach/detach behaviour is inconsistent in VR Preview

Runtime VR debugging is limited compared to editor mode


Planned Features

Robust, physics-aware VR grabbing

PSVR2-specific interactions (proper use of the haptics, and superceding OpenXR completely)

Eye-tracking interactions

Two-handed object manipulation

Snap points and precision placement (In VR Preview)

In-VR UI tools for transform editing 

Direct, automated Twinmotion export workflow

User testing and performance optimisation


Current Project Management & Development Process

Features implemented as isolated systems (Pawn, Input, Placeable Actors)

Debugging performed using:

Print Strings

Collision visualisation

Runtime logging

Risks identified early included:

VR input hardware dependency (USB-C 1.4)

Platform-specific controller mappings

Limited debugging visibility in VR Preview

Mitigations included:

Reliance on the PlayStation VR2 App

Falling back to editor-driven interaction where appropriate

Designing systems to be input-agnostic

Prioritising demonstrable progress over incomplete features
