---
name: color-palette
description: Foundational skill for creating a full color palette for design systems.
---

# Color Palette Skill

## Purpose
- Create a comprehensive color palette for design systems.
- Validate color formats, convert between color spaces, and generate color palettes.
- Provide insights into color theory and accessibility considerations.
- Validate color anatomy and inventory for a complete palette, including color lanes, steps, opacity, and modality.
- Enable color mobility for modality and theming, including light and dark modes, and color opacity lanes.

## Inputs & Environment
- **Required Inputs:** The user must provide a minimum of 3 core colors in HEX format and specify the desired number of steps for each color lane.
- **Optional Inputs:** The user may select from default color lane (15 steps) or narrow color lane (11 steps) modeled off of https://tailwindcss.com/docs/colors
- **Environment/Tools:** none.

## Step-by-Step Workflow
1. **Step One:** Ask the user to provide the required inputs.
2. **Step Two:** Establish the color palette with the followoing color lanes: neutral (gray), orange, yellow, green, teal, blue, indigo, purple, violet, pink, red, brand, and color-opacity.
3. **Step Three:** Each color lane has 11 or 15 steps depending on the color lane model. Neutral colors 2 extra stops for white and black. Color-opacity has no minimum or maximum steps, but should be named with the opacity level and step number. Each color lane should have a consistent naming convention for each step, ensuring clarity and ease of use. Step 0 is black and step 100 is white. The remaining steps should follow these steps 5, 10, 15, 20, 30, 35, 40, 50, 60, 65, 70, 80, 85, 90, 95. Narrow color lanes should follow these steps 50, 100, 200, 300, 400, 500, 600, 700, 800, 900, and 950; 0 is white and 1000 is black.
4. **Step Four:** Use the naming convention of "color lane-Step-XX" (e.g., "blue-05") for each color in the palette. Color opacity lanes should be named with the format "Color Lane-step-AXX" where the A represents the opacity level and XX represents the opacity %. (e.g., "blue-05-A50"). All in lowercase and hyphenated for consistency.
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
