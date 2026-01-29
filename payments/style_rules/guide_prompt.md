---
name: user-guide
description: |
  A skill for creating and improving comprehensive user guides from various inputs.
  It can write new guides from scratch or transform existing PRDs, meeting notes, or sketchy descriptions into polished Markdown documentation.
---

# User Guide Skill

## Overview
This skill bridges technical requirements and user-facing documentation. It creates professional user guides from scratch or transforms raw input (PRDs, notes, transcripts, sketchy descriptions) into clear, well-structured documentation that serves the user's needs.

## Capabilities
- **Content Organization**: Structure information into logical sections following proven patterns (Overview, Prerequisites, Implementation, Configuration, Troubleshooting, Related Guides).
- **Clear Instructions**: Transform complex steps into easy-to-follow, numbered instructions with UI actions bolded and code/parameters in backticks.
- **Audience Adaptation**: Tailor tone and complexity for specific audiences (developers, end-users, business stakeholders). Use second-person perspective ("your", "you").
- **Visual Communication**: Incorporate tables for scenarios/configurations, diagrams for workflows, and callout boxes (Note, Info, Warning, Tip) for important information.
- **Markdown Formatting**: Output clean, well-formatted Markdown with proper heading hierarchy and consistent styling.
- **Missing Information Identification**: Highlight gaps in provided information and ask clarifying questions to complete the guide.
- **Accessibility**: Include descriptive alt text for images. Avoid location-based descriptions. Ensure logical structure for screen readers.
- **Style Consistency**: Follow standard conventions: American spelling, no contractions, capitalized product names, proper acronym formatting.

## Usage
Provide any available information: PRD, bullet points, discussion transcript, or existing guides. Specify the target audience and desired outcome if not obvious.

## Well-Written Example Guides

### Simple Feature Guides

Refer to these well-structured guides in the existing codebase for examples:

1. **Create Orders Guide (Order Mode)** - `/payments-manual/payments/en/guides/create-orders.mdx`
   - ✅ Excellent sequence diagram showing complete workflow
   - ✅ Clear prerequisites section
   - ✅ Tabbed interface for alternative approaches (Create order vs Create order link)
   - ✅ Comprehensive scenario table with side-by-side comparison
   - ✅ Exception handling section (overpayment, underpayment, late payment)
   - ✅ Real-world workflow examples

2. **Preparation for Production Environment** - `/payments-manual/payments/en/guides/preparation-prod.mdx`
   - ✅ Organized security structure with clear sections
   - ✅ Numbered step-by-step instructions with screenshots
   - ✅ Risk control guidance with reasoning
   - ✅ Best practices callouts with specific recommendations
   - ✅ Complete workflow from setup to backup
   - ✅ Key share management with visual diagrams

3. **Checkout SDK Integration** - `/payments-manual/payments/en/guides/checkout-sdk.mdx`
   - ✅ Product features section organized by category (UX vs technical)
   - ✅ Multiple language code examples with comments
   - ✅ Prerequisites checklist before integration
   - ✅ Step-by-step implementation with code snippets
   - ✅ Event handling examples with real code
   - ✅ Configuration examples with all parameters documented

### Complex API Integration Guides

For multi-step workflows and complex integrations, refer to these examples:

1. **Callback Server Configuration** - `/developer-site-waas2/v2/guides/mpc-wallets/server-co-signer/callback-server-configure.mdx`
   - ✅ Complete configuration steps with explanations
   - ✅ Security-focused guidance throughout
   - ✅ Hands-on implementation details
   - ✅ Best practices for setup and deployment
   - ✅ Comprehensive data structures documented
   - ✅ Error handling and recovery patterns

2. **Estimate Fees** - `/developer-site-waas2/v2/guides/transactions/estimate-fees.mdx`
   - ✅ Conceptual foundation before implementation
   - ✅ Multiple scenarios covered
   - ✅ Code examples with clear parameters
   - ✅ Real response examples
   - ✅ Practical guidance on usage
   - ✅ Links to related operations

3. **Batch Transfer** - `/developer-site-waas2/v2/guides/transactions/batch-transfer.mdx`
   - ✅ Use cases and value proposition explained
   - ✅ Step-by-step workflow documentation
   - ✅ Multiple implementation options shown
   - ✅ Error handling and edge cases covered
   - ✅ Configuration and parameter flexibility
   - ✅ Related operations and guides linked

### Example Interactions

**Input**: "We added a new feature called 'Auto-Sync'. It runs every 5 minutes. Users need to enable it in Settings -> General. If it fails, check the logs."
**Output**: A structured "Auto-Sync User Guide" with overview, setup prerequisites, step-by-step enablement, troubleshooting section, and links to related features.

**Input**: "Here's a PRD for a Batch Export feature. Please write a user guide that explains the feature, how to use it, and common issues."
**Output**: A comprehensive guide including:
- Feature overview and benefits
- Prerequisites (permissions, export destination setup)
- Step-by-step instructions with UI screenshots
- Configuration options table
- Workflow diagram
- Troubleshooting for common export failures
- FAQ section

## Document Structure Pattern

A well-structured user guide typically follows this pattern:

1. **Title & Frontmatter** (metadata, lang, sidebar info)
2. **Disclaimer/Note** (if applicable, especially for AI-generated content)
3. **Overview** - What is this feature? Why would a user want to use it?
4. **Key Concepts** - Important terminology and background (if needed). Use standard terminology from Cobo's bilingual glossary.
5. **Prerequisites** - What must be done before using this feature?
   - Required permissions
   - Setup steps (links to other guides)
   - SDK installation or API key setup
6. **Implementation/How-To** - Step-by-step instructions
   - Use numbered steps
   - Bold UI elements: **Click Export**
   - Code in backticks: `batch_size`
   - Separate instructions for different methods (e.g., UI vs API) using tabs or sections
7. **Configuration Options** - Table of available settings/parameters
8. **Common Scenarios** - Different use cases with specific workflows
9. **Troubleshooting** - Common issues and solutions
10. **Workflow Diagram** - Mermaid diagram showing how the feature works
11. **Related Guides** - Links to related documentation
12. **Feedback** - Link for user feedback/bug reports

## Guidelines

- **User-Centric**: Always answer: What does the user want to accomplish? Structure the guide around their goals, not system features.
- **Imperative Language**: Use command form for instructions ("Click Export", not "You can click Export"). Use active voice throughout.
- **Clarity Over Completeness**: Prioritize clarity. If information seems unclear, ask for clarification rather than guessing.
- **Consistency**:
  - Use consistent terminology (don't alternate between "API key" and "secret key")
  - Maintain consistent formatting (bold all UI elements, backticks for all code)
  - Use American spelling (color, not colour)
- **No Contractions**: Write "It is" not "It's". Write "Do not" not "Don't".
- **Specificity**: Include enough detail for users to succeed. Avoid vague instructions like "Configure the settings" without explaining which settings.
- **Code Examples**: When including code, provide examples in relevant languages (Python, JavaScript, etc.) using tabs for alternatives.
- **Product Names**: Capitalize product names (Cobo Portal, MPC Wallets, not portal or MPC wallets)
- **Accessibility First**:
  - Use descriptive alt text: "Screenshot of Cobo Portal wallet creation dialog" not "Screenshot 1"
  - Avoid instructions like "Click the button on the left" - use UI element names instead
  - Structure with proper heading hierarchy
- **Visual Elements**: Use tables, diagrams, and callout boxes to improve scannability and comprehension.
- **Link References**: Include links to related guides, API endpoints, and reference documentation.

## 10. STANDARD TERMINOLOGY & LANGUAGE STYLE

**All writing must follow Cobo's standard terminology and language style guidelines.**

Refer to the **Reference Materials** skill for the complete guide including:
- [General Writing Rules](../reference-materials/SKILL.md#general-writing-rules) (spelling, grammar, formatting, accessibility)
- [Standard Terminology & Glossary](../reference-materials/SKILL.md#standard-terminology--glossary) (bilingual terms, product names)
- [Word Choice Rules](../reference-materials/SKILL.md#word-choice-rules) (specific words, usage patterns)

### Language and Style Rules (Summary)

1. **Perspective**: Use 2nd person ("you", "your")
   - ✅ "View your balance"
   - ❌ "View my balance"

2. **Spelling**: Use American spelling consistently
   - ✅ "color", "organize"
   - ❌ "colour", "organise"

3. **Contractions**: Avoid contractions
   - ✅ "It is ready"
   - ❌ "It's ready"
   - ✅ "Do not proceed"
   - ❌ "Don't proceed"

4. **Plurals**: Use plural nouns when possible
   - ✅ "Manage Custodial Wallets"
   - ❌ "Manage Custodial Wallet"

5. **Capitalization**:
   - Sentence case for titles (except proper nouns)
   - Capitalize product names exactly as in glossary
   - ✅ "View your balance"
   - ❌ "View Your Balance"
   - ✅ "Manage Custodial Wallets"
   - ❌ "Manage custodial wallets"

6. **Punctuation**: End each instruction step with a full stop
   - ✅ "Click Exchange Wallet."
   - ❌ "Click Exchange Wallet"

7. **UI Elements**: Bold without quotes
   - ✅ **Click Export**
   - ❌ Click "Export"
   - ❌ Click the Export button

8. **Code/Parameters**: Use backticks
   - ✅ Use the `batch_size` parameter
   - ❌ Use the batch_size parameter

### Standard Cobo Terminology

**Always use correct terminology from the bilingual glossary. Common examples:**

| Context | ✅ Use | ❌ Avoid |
|---------|--------|----------|
| Receiving money | **Payment collection**, **Pay-in** | Deposit, top-up (unless in top-up mode specifically) |
| Sending money | **Payouts**, **资金转出** | Withdrawal, transfer |
| Order mode collection | **Order mode** | Order payment, order payment mode |
| Top-up mode collection | **Top-up mode** | Top-up payment mode, deposit mode |
| Subscription mode | **Subscription mode** | Recurring mode, subscription payment mode |
| Collecting on behalf | **Collection-on-behalf-of (COBO)** | Proxy collection, behalf collection |
| Wallet management | **MPC Wallets**, **Custodial Wallets**, **Smart Contract Wallets** | MPC wallet, custodial wallet, smart contract wallet |
| Fund consolidation | **Fund sweeping** | Fund consolidation, sweeping |
| Payment processor | **Payment service provider (PSP)** | Provider, processor |
| Online sellers | **E-commerce platform** | E-commerce, online store |
| Direct sellers | **Direct-to-consumer (DTC)** | Independent website, direct website |
| Idle funds | **Idle funds** | Unused funds, excess funds |
| Risk checking | **Compliance screening**, **AML/KYT screening** | Security check, fraud check, compliance check |
| Money in | **On-ramp** | Fiat deposit, fiat conversion |
| Money out | **Off-ramp** | Fiat withdrawal, fiat conversion |
| Cryptocurrency transfer | **Crypto payouts** | Crypto transfer, asset transfer |
| Settlement | **Settlement** (in fund management) | Reconciliation, clearing |
| Amount received by merchant | **Merchant actual receipt** | Merchant received amount |
| Amount received by developer | **Developer actual receipt** | Developer received amount |
| Repay money | **Refund** | Return, give back |

### Removing Internal Jargon

Transform internal/technical terms into user-facing language:

- ❌ "状态机调整" → ✅ "状态流转逻辑优化" or "新增状态"
- ❌ "重构新接口" → ✅ "全新 API 操作"
- ❌ "App端/API端" → ✅ Remove, focus on feature category
- ❌ "上线相关交付物" → ✅ Remove (internal deliverables only)
- ❌ "系统处理" → ✅ "系统将自动" or "您的..."
- ❌ "我们添加了" → ✅ "您现在可以"
- ❌ "支持XXX功能" → ✅ "新增XXX功能，您可以..." (be specific about what user can do)

### Writing from User Perspective

Always focus on user benefits, not implementation details:

- ❌ "We refactored the authentication module"
- ✅ "Authentication response times have improved, making logins faster"

- ❌ "The system now processes transactions in batches"
- ✅ "You can now batch multiple transactions in a single request"

- ❌ "Added new status handling"
- ✅ "You can now track payment status in real-time with detailed updates"

## 11. HANDLING MISSING OR UNCLEAR INFORMATION

**When information is missing or unclear, DO NOT make assumptions. Instead:**

### Option 1: Ask Directly with Options

```
❓ Which SDK version does this feature require?
- [ ] SDK v1.30.0
- [ ] SDK v1.31.0
- [ ] Not applicable
- [ ] Other: ___________
```

### Option 2: Use Placeholders in Output

Mark unclear sections for later confirmation:

```markdown
(SDK v[VERSION]) 新增功能...
```

Or:

```markdown
[需要确认：API 端点路径]
```

### Option 3: Flag Sections for Review

```markdown
<Warning>以下信息需要确认：</Warning>
- [待确认项 1]
- [待确认项 2]
```

### Questions to Always Ask

When extracting information from messy PRDs or notes, always clarify:

- [ ] What is the exact feature name and description?
- [ ] What is the main use case or problem this solves?
- [ ] Who is the target user (merchants, developers, end-users)?
- [ ] What are the step-by-step instructions?
- [ ] What are the prerequisites?
- [ ] Which SDK version is required?
- [ ] What are the relevant API endpoints?
- [ ] Which features are deprecated (if any)?
- [ ] Are there any breaking changes?
- [ ] What are example values for all parameters?
- [ ] Are there any limitations or constraints?

**Remember:** Better to ask or use placeholders than to make incorrect assumptions.
