# Stepper

**Purpose:** Multi-step wizard / progress indicator.

## Key props (Stepper)

| Prop | Type | Description |
|------|------|-------------|
| `active` | number | Current step index (required) |
| `onStepClick` | (index) => void | Click handler for steps |
| `orientation` | `"horizontal"` \| `"vertical"` | Layout |
| `color` | MantineColor | Completed/active color |
| `allowNextStepsSelect` | boolean | Allow clicking ahead (default false) |

## Compound structure

- **Stepper.Step** — `label`, `description`, `icon`, `completedIcon`
- **Stepper.Completed** — content when all steps done

## Rules and gotchas

- Do NOT wrap Stepper.Step in other components (breaks layout)
- `active` index: steps before are completed, current is active
- `onStepClick` enables clicking on steps (with `allowNextStepsSelect` for future steps)
- Stepper.Completed content shown when `active >= steps.length`

## Example

```tsx
<Stepper active={active} onStepClick={setActive}>
  <Stepper.Step label="Info" description="Fill details" />
  <Stepper.Step label="Review" description="Check data" />
  <Stepper.Step label="Confirm" description="Submit" />
  <Stepper.Completed>Done!</Stepper.Completed>
</Stepper>
```
