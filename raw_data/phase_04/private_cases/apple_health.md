# Apple Health — System-Level Private Health

## Source date range: 2023–2024

## Scale
- iOS installed base: ~1.2B+ active iPhones globally (2024)
- Apple Health app: default on every iPhone; not a standalone product
- No user count for "Apple Health users" — it is bundled
- Not comparable to standalone apps; system-level = not a product case study

## Privacy Architecture
- On-device storage: all health data encrypted when device is locked
- iCloud sync: E2E encrypted; Apple cannot read the data
- HealthKit: third-party apps can read/write with explicit user permission
- Third-party apps prohibited from using HealthKit data for advertising or selling to data brokers (App Store policy)
- Apple white paper (May 2023): "Apple works to minimize health data it collects"

## Monetization
- NONE from health data: Apple does not monetize Apple Health data
- Indirect: Apple Watch sales driven by Health features
- Apple Fitness+ subscription: $9.99/mo or $79.99/yr (bundled with Apple One)
- Research app: users can opt-in to Apple research studies (Apple Heart Study, etc.) — purely opt-in, IRB-approved

## % Users Public
- 0%: Apple Health has no social/public layer

## Fit with "Feed B-Side Data" Goal
- ZERO fit: intentional architecture prevents any B2B data path
- Lesson: privacy-as-brand-feature drives hardware premium; monetization through device, not data

## Sources
- apple.com/legal/privacy/data/en/health-app
- apple.com/privacy/docs/Health_Privacy_White_Paper_May_2023.pdf
- 9to5mac.com/2023/05/24/apple-health-privacy
- apple.com/newsroom/2024/09/apple-introduces-groundbreaking-health-features
