---
name: color-palette
description: Foundational skill for creating a full color palette for design systems.
---

# Color Palette Skill

## Purpose
- Contextualize and manipulate visual color data for applications in design, analysis, and visualization.
- Validate color formats, convert between color spaces, and generate color palettes.
- Provide insights into color theory and accessibility considerations.
- Validate color anatomy and inventory for a complete palette, including color lanes, steps, opacity, and modality.

## Inputs & Environment
- **Required Inputs:** The user must provide a minimum of 3 core colors in HEX format and specify the desired number of steps for each color lane.
- **Environment/Tools:** none.

## Step-by-Step Workflow
1. **Step One:** Ask the user to provide the required inputs.
2. **Step Two:** Establish the color palette with the followoing color lanes: Neutral (gray), Orange, Yellow, Green, Teal, Blue, Indigo, Purple, Violet, Pink, Red, brand, color-opacity.
3. **Step Three:** Each color lane has 15 steps. Neutral colors 2 extra stops for white and black. Color-opacity has no minimum or maximum steps, but should be named with the opacity level and step number. Each color lane should have a consistent naming convention for each step, ensuring clarity and ease of use.
4. **Step Four:** Use the naming convention of "Color Lane-Step-XX" (e.g., "Blue-05") for each color in the palette. Color opacity lanes should be named with the format "Color Lane-step-AXX" where the A represents the opacity level and XX represents the opacity %. (e.g., "Blue-05-A50").
5. **Step Five:** Validate the color palette for accessibility, ensuring sufficient contrast ratios and adherence to WCAG guidelines.
6. **Step Six:** Document the final color palette, including color codes (HEX, RGB, HSL), opacity levels, and any relevant notes on usage or context.
7. **Step Seven:** Test color contrast to meet accessibility standards of 4.5:1 when the step number is 50 or greater. Example, blue-10 will pass with blue-60. Differance between the two is 50 steps. If the step number is less than 50, the contrast ratio should be 3:1. Example, blue-10 will pass with blue-40. Differance between the two is 30 steps.

## Anti-Patterns (What NOT to do)
- Do not explain things the AI already knows.
- Do not skip validation or formatting steps.
- Do not use inconsistent naming conventions for color lanes and steps.
- Do not ignore accessibility standards and contrast ratios.
- Do not create any color-opacity lanes without proper naming conventions and opacity levels.
- Do not create any color-opacity lanes not defined from the user's input or the established color palette.

## Output Format
- Design Token file, in JSON that adheres to the specified naming conventions and includes all relevant color data and wht DTCG Group spec. https://www.designtokens.org/tr/drafts/format/
