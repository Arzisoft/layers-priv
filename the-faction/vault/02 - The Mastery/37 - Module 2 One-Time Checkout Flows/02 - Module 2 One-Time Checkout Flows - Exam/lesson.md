---
course: "The Mastery"
module: "Module 2: One-Time Checkout Flows"
lesson: "Module 2: One-Time Checkout Flows — Exam"
type: "course_quiz"
post_id: 106562771
space_id: 24191170
source: "https://the-faction.mn.co/posts/106562771"
updated: "2026-08-28T16:03:38Z"
---

# Module 2: One-Time Checkout Flows — Exam

> Exam for **Module 2: One-Time Checkout Flows** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder is shipping her first one-time purchase flow and asks whether to direct AI toward hosted Checkout, embedded Checkout, or a fully custom payment form. There is no unusual brand requirement. What is the professional default?

- **A.** Fully custom with Payment Element, because owning every pixel of checkout is worth the extra build surface
- **B.** Hosted Checkout, because it ships fastest, minimizes PCI burden, and is conversion-optimized by Stripe  ✅
- **C.** Embedded Checkout, because keeping the customer on your domain always outperforms any redirect design
- **D.** A Payment Link, because generated URLs replace the need for any integration work on real products

> **Answer:** B

### Q2. A store fulfills orders the moment customers land on the success page after paying. Occasionally paid customers report never receiving their product. What is the most likely cause?

- **A.** Stripe delayed settlement on those orders, so fulfillment logic correctly waited for funds to clear first
- **B.** The success page cached an older order state, so fulfillment fired against stale session identifiers
- **C.** Those customers used cards requiring authentication, which always suppresses the final redirect step
- **D.** The redirect never fired for those customers, and fulfillment depended on it instead of the webhook  ✅

> **Answer:** D

### Q3. During an audit you find the checkout session is created using a total amount sent from the browser's cart JavaScript. Why is this a critical finding?

- **A.** Browser-computed totals drift from server totals whenever tax rates change during an active session
- **B.** Client-side amounts get rounded differently across browsers, producing small reconciliation gaps
- **C.** Anyone can edit the amount in their browser before submission and buy the product at any price they choose  ✅
- **D.** Stripe rejects amounts that arrive without a signed catalog reference attached to the API request

> **Answer:** C

### Q4. A founder hardcodes dollar amounts into every checkout call instead of modeling anything in Stripe. Six months later, what predictable problem has this created?

- **A.** Revenue reporting is meaningless and price changes require hunting down amounts scattered across the build  ✅
- **B.** Stripe has begun rejecting the calls, because ad-hoc amounts are deprecated for accounts past a volume tier
- **C.** Currency conversion has silently failed, because inline amounts cannot carry currency codes with them
- **D.** Checkout conversion has dropped, because sessions without product objects render without descriptions

> **Answer:** A

### Q5. A customer opens checkout, gets distracted, and returns two days later to the same session URL. The link no longer works. What should the builder understand about this situation?

- **A.** The session hit a Stripe error state and support must manually release it before a retry can happen
- **B.** The customer's cart is now corrupted and the product must be re-added before any new attempt works
- **C.** Sessions expire by design, so the app should simply create a fresh session from the cart when they return  ✅
- **D.** The account has a session quota and stale sessions consume slots until they are explicitly deleted

> **Answer:** C

### Q6. A webhook fires for a completed checkout, and the handler needs to figure out which internal order it belongs to. What should have been done at session creation to make this trivial?

- **A.** Naming the session after the customer's email so the handler can match on the address string later
- **B.** Attaching the internal order ID via client_reference_id or metadata when the session was created  ✅
- **C.** Storing the Stripe session URL in the order table so the handler can compare full URLs on receipt
- **D.** Delaying order creation until after payment so no matching between systems is ever necessary at all

> **Answer:** B

### Q7. A teammate asks what actually happened, on Stripe's side, when a customer clicks away from checkout and lands on the cancel URL. What is accurate?

- **A.** A failed payment was recorded against the customer and will appear in decline analytics for the account
- **B.** The payment is held in a pending state for 24 hours in case the customer decides to return and finish
- **C.** A partial authorization occurred and will be automatically reversed during the next settlement batch run
- **D.** Nothing was charged, and the cancel URL simply returns the customer to shopping with no payment record  ✅

> **Answer:** D

### Q8. A builder directing a one-time purchase flow asks which session mode to specify and why it matters. What do you tell her?

- **A.** Mode payment, because it configures the session for a one-time charge rather than a recurring subscription  ✅
- **B.** Mode setup, because collecting the payment method first is required before any charge can be created
- **C.** Mode subscription with a one-cycle price, because single charges are modeled as short subscriptions
- **D.** No mode at all, because Stripe infers the correct behavior from the structure of the line items sent

> **Answer:** A

### Q9. The success page needs to show the customer an accurate order confirmation. The session ID is available in the URL. What is the professional pattern?

- **A.** Render the confirmation from values stored in the browser before redirect, avoiding any server round trip
- **B.** Retrieve the session server-side using the ID and display its actual status and details to the customer  ✅
- **C.** Parse the payment amount out of the referrer header, since Stripe includes totals in redirect headers
- **D.** Show a generic thank-you with no order details, since accurate data is never available at redirect time

> **Answer:** B

### Q10. A coach wants to sell a single digital workshop this weekend to test demand before directing any real build. What is the fastest professional move?

- **A.** Direct a full hosted Checkout integration now, since a weekend is enough time to ship the whole flow
- **B.** Collect card numbers through a form and charge them manually from the dashboard as orders arrive
- **C.** Create a Payment Link from the dashboard and share the URL, deferring integration until demand is proven  ✅
- **D.** Set up invoicing and send each interested buyer a personal invoice as replies come in over the weekend

> **Answer:** C

### Q11. A product team insists checkout must live inside their page layout with their surrounding content, but wants Stripe to keep handling the payment form itself. What do you direct AI to build?

- **A.** Embedded Checkout, which renders Stripe's checkout engine inside your page instead of redirecting away  ✅
- **B.** Hosted Checkout with custom CSS injection, since the hosted page accepts arbitrary style overrides
- **C.** An iframe wrapping the hosted page URL, which achieves embedding without any additional integration work
- **D.** A screenshot-matched replica of Stripe's form posting to the charges endpoint from your own backend

> **Answer:** A

### Q12. A builder asks what a line item in a checkout session should reference in a well-modeled build. What is the professional answer?

- **A.** A raw amount and description typed inline, keeping the catalog logic entirely inside the application code
- **B.** A product ID alone, since prices are resolved automatically from the product's default configuration
- **C.** A customer ID, since line items bind the purchase to the buyer rather than to the catalog entries
- **D.** A price object from the catalog, so amounts, currency, and reporting all trace to one source of truth  ✅

> **Answer:** D

### Q13. A store sells to the US and Germany. The founder asks how to handle charging euros to German customers without directing a second codebase. What is the clean approach?

- **A.** Charge everyone in dollars and let the customer's bank handle conversion at whatever rate applies that day
- **B.** Create per-currency prices on the same products and select the right price based on the customer's market  ✅
- **C.** Run a second Stripe account registered in Germany and route European traffic to that account instead
- **D.** Convert amounts in application code using a daily exchange rate feed before creating each session

> **Answer:** B

### Q14. A founder worries about translating the checkout page for international customers. What should the builder know about locale in hosted Checkout?

- **A.** Checkout renders only in the account's registered business language unless a paid add-on is enabled
- **B.** Each supported language requires its own session template maintained separately in the dashboard
- **C.** Checkout can auto-detect the customer locale and render its interface in the appropriate language  ✅
- **D.** Locale is controlled by the product descriptions, so the catalog must be duplicated per language

> **Answer:** C

### Q15. During review you ask where checkout sessions get created in a build. Which answer indicates the build is structured correctly?

- **A.** Server-side, where the amount comes from the catalog and secrets stay out of the browser entirely  ✅
- **B.** In the browser using the publishable key, keeping payment logic close to the user interaction layer
- **C.** In a scheduled job that pre-creates a pool of sessions each morning for the day's expected traffic
- **D.** Inside the webhook handler, so session creation and fulfillment share one code path end to end

> **Answer:** A

### Q16. A builder asks what Stripe actually knows about the customer's cart during checkout. What is the accurate mental model?

- **A.** Stripe mirrors your cart database in real time once the first session for that customer is created
- **B.** Stripe crawls your product pages to build its own catalog and reconciles it against each session
- **C.** Stripe receives the full cart history including removed items so disputes can reference behavior
- **D.** Stripe sees only the line items you send at session creation; the cart itself lives in your application  ✅

> **Answer:** D

### Q17. An app keeps a session ID in the database and reuses it whenever the customer returns to buy again. Payments intermittently fail. What is the correct fix?

- **A.** Extend the session expiration window in the dashboard so stored sessions stay valid for far longer
- **B.** Treat sessions as disposable and create fresh ones per purchase attempt instead of reusing old IDs  ✅
- **C.** Retry the stored session with exponential backoff until Stripe accepts it and completes the payment
- **D.** Attach a new payment intent to the stored session at each visit so the old shell can keep working

> **Answer:** B

### Q18. A design-driven founder wants a fully custom payment form for brand reasons alone. What tradeoff must you make sure she understands before directing that build?

- **A.** She inherits edge cases Stripe already solved: authentication flows, wallets, validation, and more compliance surface  ✅
- **B.** Custom forms cannot support Apple Pay or Google Pay, which only function on Stripe-hosted domains and checkout surfaces
- **C.** Custom forms settle funds a full day slower, because manual review applies to non-hosted integrations
- **D.** Stripe charges a higher per-transaction rate whenever payments originate from custom-built forms by policy

> **Answer:** A

### Q19. A builder claims checkout is done because a test purchase with the standard test card succeeded. What testing is still missing before this claim is credible?

- **A.** A load test proving the checkout endpoint can handle at least one thousand concurrent sessions
- **B.** A test in every supported browser, since payment element rendering differs across engine versions in practice
- **C.** Decline cards, an abandoned session, and the cancel path, because the unhappy paths are where builds fail  ✅
- **D.** A penetration test of the hosted checkout page itself before any real customer traffic reaches it

> **Answer:** C

### Q20. A customer refreshes the success page five times. The build fulfills the order once and only once. Which design choice made this safe?

- **A.** The success URL includes a nonce that the browser strips after first load, blocking repeat renders
- **B.** The page immediately redirects to the homepage after rendering once, preventing any refresh at all
- **C.** Sessions self-destruct after the first success page view, so later refreshes have nothing to load
- **D.** Fulfillment hangs off the webhook with idempotent handling, so page views never trigger it at all  ✅

> **Answer:** D

### Q21. A product costs 50 dollars for US buyers and 45 euros for EU buyers. Where should this pricing live in a professional build?

- **A.** As two price objects on one product in the catalog, selected by market at session creation time  ✅
- **B.** As one USD price with the conversion multiplier applied in application code for European sessions
- **C.** As two separate products, since Stripe treats each currency as a distinct catalog entry anyway
- **D.** As inline amounts per session, since multi-currency catalogs require the platform account type

> **Answer:** A

### Q22. A builder wants the success page to know which session just completed. How does the session ID reach the success URL in hosted Checkout?

- **A.** Stripe sets a cookie on your domain during redirect that the success page reads on first load of the page
- **B.** You include a template placeholder in the success URL and Stripe substitutes the session ID on redirect  ✅
- **C.** The session ID arrives in a POST body that Stripe sends to the success URL after the redirect
- **D.** The browser's referrer header carries the ID, which the success page parses out on arrival

> **Answer:** B

### Q23. A finance lead asks why March revenue cannot be broken down by product. The build passes ad-hoc amounts for everything. What is the connection?

- **A.** Ad-hoc amounts settle into a pooled balance that Stripe cannot attribute to any revenue category or product
- **B.** The dashboard only reports on payments made through Payment Links, not API-created sessions
- **C.** Without products and prices, Stripe has no catalog dimension to report against, so revenue is one blob  ✅
- **D.** Reporting requires the invoicing add-on, which is unavailable to accounts using direct charges

> **Answer:** C

### Q24. A founder asks why you keep recommending hosted Checkout over a hand-built form for his first launch, beyond build speed. What is the conversion argument?

- **A.** Hosted pages rank in search results, so the checkout URL itself becomes an acquisition channel
- **B.** Customers trust any page more when the browser address bar shows a stripe.com domain during payment entry
- **C.** Hosted Checkout removes all payment friction categories, so abandonment approaches zero at scale
- **D.** Stripe continuously optimizes the hosted flow across billions of payments, testing you cannot replicate  ✅

> **Answer:** D

### Q25. Looking across everything in this module, what is the governing principle for one-time checkout flows?

- **A.** Compute truth server-side and treat the redirect as UX, because payment state must never depend on a browser  ✅
- **B.** Maximize checkout customization from day one, because brand differentiation is what wins conversion
- **C.** Keep the catalog in application code, because Stripe objects add indirection without real benefit
- **D.** Fulfill instantly on redirect, because making customers wait for webhooks measurably damages trust

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/106562771_
