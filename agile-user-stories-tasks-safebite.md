# SafeBite — User Stories and Tasks

**Project:** SafeBite  
**Project Type:** Entrepreneurial WIL Project  
**Development Approach:** Agile

## 1. Introduction

This document describes the user stories and development tasks for SafeBite, a mobile-first HealthTech application. User stories explain the needs of different users, while tasks identify the work required to support those needs.

The stories are based on the features described in the SafeBite project documentation. They should be reviewed against the functionality actually implemented by the team.

## 2. User Stories

### US01: Scan a Food Product

**As a** consumer,  
**I want** to scan a food product's barcode,  
**So that** I can access product information and a personalised food safety analysis.

**Acceptance criteria:**
- The user can open the barcode scanning feature.
- A supported barcode can be scanned.
- Available product information is displayed.
- The application presents a safety analysis when the required information is available.

**Tasks:**
- Develop the barcode scanning interface.
- Connect scanning results to the product information service.
- Display product details and the safety verdict.
- Test supported barcode formats and invalid scans.

**Priority:** High

### US02: Analyse an Ingredient Label

**As a** consumer,  
**I want** to photograph an ingredients label,  
**So that** I can check a product even when it has no barcode or is missing from the product database.

**Acceptance criteria:**
- The user can capture or select an ingredient-label image.
- The image is submitted for analysis.
- Recognised ingredient information is processed.
- The application displays the available analysis results.

**Tasks:**
- Create the ingredient-label image input interface.
- Integrate the image-analysis functionality.
- Process the recognised ingredient information.
- Test image quality and unsuccessful analysis scenarios.

**Priority:** High

### US03: Maintain a Personal Health Profile

**As a** user,  
**I want** to record my allergies, medical conditions, dietary preferences and medications,  
**So that** food safety information can be personalised to my needs.

**Acceptance criteria:**
- The user can enter and update supported health profile information.
- Saved information can be retrieved.
- The relevant profile is used by supported personalisation features.
- Profile information is handled securely.

**Tasks:**
- Create or maintain the health profile interface.
- Connect the interface to the relevant data storage.
- Validate profile inputs.
- Test saving, retrieving and updating profile information.

**Priority:** High

### US04: Identify Potential Allergen Risks

**As a** user with food allergies,  
**I want** the application to identify relevant allergens in a product,  
**So that** I can make a more informed food choice.

**Acceptance criteria:**
- The analysis uses the user's recorded allergies where supported.
- Recognised allergen names and synonyms are checked.
- Potential matches are clearly highlighted.
- Uncertain or incomplete ingredient information is not presented as a guarantee of safety.

**Tasks:**
- Implement or integrate allergen matching.
- Check relevant ingredient names and synonyms.
- Display allergen warnings.
- Test matching and non-matching examples.

**Priority:** High

### US05: Check Restaurant Menus

**As a** user eating at a restaurant,  
**I want** to photograph a menu,  
**So that** I can review potential food safety concerns before choosing a dish.

**Acceptance criteria:**
- The user can submit a menu photograph.
- The application analyses recognised dishes.
- Available results show Safe, Caution or Avoid ratings.
- Relevant warnings are displayed for the active profile.

**Tasks:**
- Create the menu scanning interface.
- Integrate menu image analysis.
- Display dish names and ratings.
- Test menus with different layouts and image quality.

**Priority:** Medium

### US06: Receive Food Recall Alerts

**As a** consumer,  
**I want** to be notified when a previously scanned product is recalled,  
**So that** I can respond to relevant food safety information.

**Acceptance criteria:**
- Previously scanned products can be checked against available recall data.
- Matching recall information is displayed.
- Relevant alerts are presented to the user.
- Where implemented, recall severity reflects relevant profile information.

**Tasks:**
- Connect to the openFDA food recall feed.
- Match scanned products against available recall information.
- Create the recall alert interface.
- Test matching, missing data and notification behaviour.

**Priority:** High

### US07: Use the Sage AI Assistant

**As a** SafeBite user,  
**I want** to ask the Sage assistant questions about food,  
**So that** I can receive guidance relevant to my profile and scanned products.

**Acceptance criteria:**
- The user can open the Sage assistant.
- The user can submit a question.
- The assistant returns a response when the service is available.
- Relevant profile context is used where supported.
- Responses are presented as informational guidance rather than a substitute for professional medical advice.

**Tasks:**
- Develop the chat interface.
- Integrate the Google Gemini service.
- Pass relevant context according to the application's design.
- Handle loading states and service errors.
- Test the assistant's responses and user experience.

**Priority:** Medium

### US08: Manage Food Inventory

**As a** shopkeeper,  
**I want** to add, edit and remove products and track their stock and expiry dates,  
**So that** I can manage inventory and identify products that need attention.

**Acceptance criteria:**
- The shopkeeper can add a product.
- Existing product details can be updated or deleted.
- Stock and expiry information can be viewed.
- The dashboard displays relevant inventory statistics where implemented.
- Shopkeeper data is protected by the appropriate access controls.

**Tasks:**
- Develop the inventory management interface.
- Connect product operations to Supabase.
- Implement stock and expiry information displays.
- Create or maintain inventory dashboard statistics.
- Test product management and access permissions.

**Priority:** High

### US09: View the SafeBite Dashboard

**As a** SafeBite user,  
**I want** to view a dashboard with relevant information and shortcuts,  
**So that** I can access important features conveniently.

**Acceptance criteria:**
- The dashboard displays the relevant information for its intended user.
- Available navigation options lead to the correct features.
- Information is displayed clearly on the supported screen sizes.
- Loading and empty states are handled appropriately.

**Tasks:**
- Develop and maintain `Dashboard.jsx`.
- Connect dashboard components to the relevant data sources.
- Add navigation to supported features.
- Test dashboard layout and interactions.
- Fix any identified display or navigation issues.

**Priority:** High

## 3. Task Prioritisation

| Priority | Meaning |
|---|---|
| High | Important functionality central to the application or its core user needs. |
| Medium | Useful functionality that supports the overall user experience. |
| Low | Enhancements that can be scheduled after higher-priority work. |

Priorities are proposed for planning purposes and should be confirmed by the project team.

## 4. Task Tracking

Each task should be tracked using the team's agreed project management process.

Suggested statuses:

- To Do
- In Progress
- Review
- Completed

A task should only be marked Completed after the required work has been performed and checked.

## 5. Reflection

Writing user stories helps connect software requirements to the needs of the people who will use the application. Breaking stories into smaller tasks makes the work easier to plan, assign and track. For SafeBite, this approach helps the team organise a wide range of features while keeping the user experience and food safety objectives in focus.
