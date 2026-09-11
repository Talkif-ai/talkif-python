# Reference
## Billing
<details><summary><code>client.billing.<a href="src/talkif/billing/client.py">get_balance_summary</a>() -> BalanceSummaryResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/billing/balances
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.billing.get_balance_summary()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.billing.<a href="src/talkif/billing/client.py">list_charges</a>(...) -> PaginatedResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Paginated, filterable charge history for an account.
Returns charges with entity context (phone number, flow name, contact name)
from the first associated cost line item.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.billing.list_charges()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `typing.Optional[int]` — Page size (max 100)
    
</dd>
</dl>

<dl>
<dd>

**offset:** `typing.Optional[int]` — Page offset
    
</dd>
</dl>

<dl>
<dd>

**charge_type:** `typing.Optional[ChargeTypeDb]` — Filter by charge type
    
</dd>
</dl>

<dl>
<dd>

**status:** `typing.Optional[ChargeStatus]` — Filter by status
    
</dd>
</dl>

<dl>
<dd>

**start_date:** `typing.Optional[str]` — Filter from date (inclusive)
    
</dd>
</dl>

<dl>
<dd>

**end_date:** `typing.Optional[str]` — Filter to date (inclusive)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.billing.<a href="src/talkif/billing/client.py">get_charge_detail</a>(...) -> ChargeDetailResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Detailed charge view with cost line items breakdown.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.billing.get_charge_detail(
    charge_id="chargeId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**charge_id:** `str` — Charge ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.billing.<a href="src/talkif/billing/client.py">get_billing_cost_breakdown</a>(...) -> AnalyticsCostBreakdownResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get account-level cost breakdown by category with drill-down to calls.

## Query Parameters
- `period`: `today`, `week`, `month`, or `custom` (default: `week`)
- `startDate`: Required when `period=custom`
- `endDate`: Required when `period=custom`

## Response
Returns total costs, breakdown by category (LLM, STT, TTS, telephony),
breakdown by flow, and recent calls with individual cost breakdowns.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.billing.get_billing_cost_breakdown()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**period:** `typing.Optional[str]` — Time period: today, week, month, or custom
    
</dd>
</dl>

<dl>
<dd>

**start_date:** `typing.Optional[str]` — Start date for custom period
    
</dd>
</dl>

<dl>
<dd>

**end_date:** `typing.Optional[str]` — End date for custom period
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.billing.<a href="src/talkif/billing/client.py">get_billing_call_cost_breakdown</a>(...) -> CallCostBreakdownResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get detailed cost breakdown for a single call with line items.

Returns all cost line items including usage data (tokens, seconds, characters)
and rate information for each cost component.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.billing.get_billing_call_cost_breakdown(
    call_id="callId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**call_id:** `str` — Call ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.billing.<a href="src/talkif/billing/client.py">list_invoices</a>(...) -> PaginatedResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/billing/invoices
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.billing.list_invoices()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `typing.Optional[int]` — Page size
    
</dd>
</dl>

<dl>
<dd>

**offset:** `typing.Optional[int]` — Page offset
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.billing.<a href="src/talkif/billing/client.py">get_invoice</a>(...) -> InvoiceResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/billing/invoices/{invoiceId}
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.billing.get_invoice(
    invoice_id="invoiceId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**invoice_id:** `str` — Invoice ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.billing.<a href="src/talkif/billing/client.py">get_transaction_history</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/billing/transactions
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.billing.get_transaction_history()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `typing.Optional[int]` — Max items to return
    
</dd>
</dl>

<dl>
<dd>

**offset:** `typing.Optional[int]` — Items to skip
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.billing.<a href="src/talkif/billing/client.py">get_public_pricing</a>() -> PublicPricingResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Public endpoint — no authentication required.
Returns telephony rates, phone number pricing, and recording storage pricing.

LLM/STT/TTS pricing is served by `GET /api/v1/models/*` with richer data
(capabilities, languages, use-case filtering).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.billing.get_public_pricing()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Calls
<details><summary><code>client.calls.<a href="src/talkif/calls/client.py">make_call</a>(...) -> MakeCallResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

POST /api/v1/calls

SECURITY: Verifies account access, phone ownership, provider ownership, flow ownership

Returns:
- 201 Created: Call initiated immediately (capacity available)
- 202 Accepted: Call queued for later processing (at capacity/rate limited)
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.calls.make_call(
    flow_id="550e8400-e29b-41d4-a716-446655440000",
    from_number="+15559876543",
    provider_id="550e8400-e29b-41d4-a716-446655440000",
    to_number="+15551234567",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**flow_id:** `str` — Flow ID to use for the AI conversation
    
</dd>
</dl>

<dl>
<dd>

**from_number:** `str` — Caller phone number in E.164 format, must be owned by the account
    
</dd>
</dl>

<dl>
<dd>

**provider_id:** `str` — Provider ID to route the call through
    
</dd>
</dl>

<dl>
<dd>

**to_number:** `str` — Destination phone number in E.164 format (emergency numbers blocked)
    
</dd>
</dl>

<dl>
<dd>

**campaign_contact_id:** `typing.Optional[str]` — Campaign contact ID for per-contact status tracking
    
</dd>
</dl>

<dl>
<dd>

**campaign_id:** `typing.Optional[str]` — Campaign ID if this call is part of a bulk campaign
    
</dd>
</dl>

<dl>
<dd>

**contact_id:** `typing.Optional[str]` — Contact ID to associate with this call
    
</dd>
</dl>

<dl>
<dd>

**flow_version:** `typing.Optional[str]` — Flow version to use, defaults to current published version
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `typing.Optional[typing.Dict[str, typing.Any]]` — Additional metadata to attach to the call
    
</dd>
</dl>

<dl>
<dd>

**source:** `typing.Optional[CallSource]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.calls.<a href="src/talkif/calls/client.py">get_active_calls</a>() -> typing.List[CallResponse]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/calls/active
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.calls.get_active_calls()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.calls.<a href="src/talkif/calls/client.py">get_call_history</a>() -> CallListResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/calls/history
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.calls.get_call_history()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.calls.<a href="src/talkif/calls/client.py">get_call_details</a>(...) -> CallResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/calls/:callId
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.calls.get_call_details(
    call_id="callId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**call_id:** `str` — Call ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.calls.<a href="src/talkif/calls/client.py">analyze_call</a>(...) -> typing.Optional[CallInsights]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

POST /api/v1/calls/:callId/analyze

Generates AI-powered insights from the call transcript:
- Summary (2-3 sentences)
- Sentiment analysis (positive/neutral/negative + confidence)
- Detected intents
- Key topics discussed
- Action items
- Call outcome

This endpoint is always available regardless of account auto-analysis settings.
Can be used to:
- Analyze calls that weren't auto-analyzed
- Re-analyze calls with updated AI model

Requires the call to be in a terminal state (COMPLETED/FAILED/etc.)
and have a transcript available.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.calls.analyze_call(
    call_id="callId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**call_id:** `str` — Call ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.calls.<a href="src/talkif/calls/client.py">get_call_recording</a>(...) -> RecordingUrlResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a time-limited presigned URL for recording playback. Fetch the audio directly from that URL.

Requires the call to belong to the account and to have `recordingStatus = ready`; recording must be enabled for the account.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.calls.get_call_recording(
    call_id="callId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**call_id:** `str` — Call ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.calls.<a href="src/talkif/calls/client.py">delete_call_recording</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

DELETE /api/v1/calls/:callId/recording → 204

Charges for actual storage duration before deletion (billing at lifecycle end).
Uses idempotency key to prevent double-charging if racing with retention job.

SECURITY: Verifies account access, call ownership.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.calls.delete_call_recording(
    call_id="callId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**call_id:** `str` — Call ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.calls.<a href="src/talkif/calls/client.py">get_call_transcript</a>(...) -> CallTranscriptResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/calls/:callId/transcript
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.calls.get_call_transcript(
    call_id="callId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**call_id:** `str` — Call ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Campaigns
<details><summary><code>client.campaigns.<a href="src/talkif/campaigns/client.py">list_campaigns</a>(...) -> CampaignListResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.campaigns.list_campaigns()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**status:** `typing.Optional[CampaignStatus]` — Filter by status
    
</dd>
</dl>

<dl>
<dd>

**search:** `typing.Optional[str]` — Case-insensitive search over name and description
    
</dd>
</dl>

<dl>
<dd>

**limit:** `typing.Optional[int]` — Max items to return
    
</dd>
</dl>

<dl>
<dd>

**offset:** `typing.Optional[int]` — Items to skip
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.campaigns.<a href="src/talkif/campaigns/client.py">create_campaign</a>(...) -> CampaignResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.campaigns.create_campaign(
    flow_id="550e8400-e29b-41d4-a716-446655440000",
    from_phone_number="+15551234567",
    name="January Outreach",
    provider_id="550e8400-e29b-41d4-a716-446655440000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**flow_id:** `str` — Flow (conversation script) to use for all calls
    
</dd>
</dl>

<dl>
<dd>

**from_phone_number:** `str` — Caller ID phone number in E.164 format
    
</dd>
</dl>

<dl>
<dd>

**name:** `str` — Human-readable name for the campaign
    
</dd>
</dl>

<dl>
<dd>

**provider_id:** `str` — VoIP provider to route calls through
    
</dd>
</dl>

<dl>
<dd>

**allowed_days:** `typing.Optional[typing.List[int]]` — DEPRECATED: Use call_windows instead. Allowed days of week (1=Monday through 7=Sunday)
    
</dd>
</dl>

<dl>
<dd>

**call_windows:** `typing.Optional[typing.List[CallWindowRequest]]` — Call time windows in UTC, if empty or not provided calls are allowed anytime
    
</dd>
</dl>

<dl>
<dd>

**concurrent_calls:** `typing.Optional[int]` — Maximum number of simultaneous calls (1-50), defaults to 5
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Optional description of the campaign purpose
    
</dd>
</dl>

<dl>
<dd>

**earliest_call_time:** `typing.Optional[str]` — DEPRECATED: Use call_windows instead. Earliest time to call (HH:MM)
    
</dd>
</dl>

<dl>
<dd>

**end_at:** `typing.Optional[datetime.datetime]` — End time after which the campaign auto-pauses, must be after start_at
    
</dd>
</dl>

<dl>
<dd>

**latest_call_time:** `typing.Optional[str]` — DEPRECATED: Use call_windows instead. Latest time to call (HH:MM)
    
</dd>
</dl>

<dl>
<dd>

**respect_contact_timezone:** `typing.Optional[bool]` — Whether to check each contact's timezone before calling, defaults to true
    
</dd>
</dl>

<dl>
<dd>

**start_at:** `typing.Optional[datetime.datetime]` — Scheduled start time, if null user must manually start the campaign
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.campaigns.<a href="src/talkif/campaigns/client.py">get_campaign</a>(...) -> CampaignResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.campaigns.get_campaign(
    campaign_id="campaignId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**campaign_id:** `str` — Campaign ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.campaigns.<a href="src/talkif/campaigns/client.py">update_campaign</a>(...) -> CampaignResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.campaigns.update_campaign(
    campaign_id="campaignId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**campaign_id:** `str` — Campaign ID
    
</dd>
</dl>

<dl>
<dd>

**allowed_days:** `typing.Optional[typing.List[int]]` — DEPRECATED: Use call_windows instead. Allowed days of week (1=Monday through 7=Sunday)
    
</dd>
</dl>

<dl>
<dd>

**call_windows:** `typing.Optional[typing.List[CallWindowRequest]]` — Call time windows in UTC, replaces all existing windows (empty array clears all)
    
</dd>
</dl>

<dl>
<dd>

**concurrent_calls:** `typing.Optional[int]` — Maximum number of simultaneous calls (1-50)
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Optional description of the campaign purpose
    
</dd>
</dl>

<dl>
<dd>

**earliest_call_time:** `typing.Optional[str]` — DEPRECATED: Use call_windows instead. Earliest time to call (HH:MM)
    
</dd>
</dl>

<dl>
<dd>

**end_at:** `typing.Optional[datetime.datetime]` — End time after which the campaign auto-pauses, must be after start_at
    
</dd>
</dl>

<dl>
<dd>

**latest_call_time:** `typing.Optional[str]` — DEPRECATED: Use call_windows instead. Latest time to call (HH:MM)
    
</dd>
</dl>

<dl>
<dd>

**name:** `typing.Optional[str]` — Human-readable name for the campaign
    
</dd>
</dl>

<dl>
<dd>

**respect_contact_timezone:** `typing.Optional[bool]` — Whether to check each contact's timezone before calling
    
</dd>
</dl>

<dl>
<dd>

**start_at:** `typing.Optional[datetime.datetime]` — Scheduled start time, must be in the future if provided
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.campaigns.<a href="src/talkif/campaigns/client.py">delete_campaign</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.campaigns.delete_campaign(
    campaign_id="campaignId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**campaign_id:** `str` — Campaign ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.campaigns.<a href="src/talkif/campaigns/client.py">cancel_campaign</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.campaigns.cancel_campaign(
    campaign_id="campaignId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**campaign_id:** `str` — Campaign ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.campaigns.<a href="src/talkif/campaigns/client.py">list_campaign_contacts</a>(...) -> CampaignContactListResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.campaigns.list_campaign_contacts(
    campaign_id="campaignId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**campaign_id:** `str` — Campaign ID
    
</dd>
</dl>

<dl>
<dd>

**status:** `typing.Optional[CampaignContactStatus]` — Filter by derived contact status
    
</dd>
</dl>

<dl>
<dd>

**search:** `typing.Optional[str]` — Case-insensitive search over phone number, name and email
    
</dd>
</dl>

<dl>
<dd>

**limit:** `typing.Optional[int]` — Max items to return (1-100)
    
</dd>
</dl>

<dl>
<dd>

**offset:** `typing.Optional[int]` — Items to skip
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.campaigns.<a href="src/talkif/campaigns/client.py">add_campaign_contacts</a>(...) -> AddedResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.campaigns.add_campaign_contacts(
    campaign_id="campaignId",
    contact_ids=[
        "contactIds"
    ],
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**campaign_id:** `str` — Campaign ID
    
</dd>
</dl>

<dl>
<dd>

**contact_ids:** `typing.List[str]` — List of contact IDs to add (1-1000 per request)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.campaigns.<a href="src/talkif/campaigns/client.py">remove_campaign_contacts</a>(...) -> RemovedResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.campaigns.remove_campaign_contacts(
    campaign_id="campaignId",
    campaign_contact_ids=[
        "campaignContactIds"
    ],
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**campaign_id:** `str` — Campaign ID
    
</dd>
</dl>

<dl>
<dd>

**campaign_contact_ids:** `typing.List[str]` — Campaign contact IDs to remove (1-1000), use IDs from the list contacts response
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.campaigns.<a href="src/talkif/campaigns/client.py">bulk_add_campaign_contacts</a>(...) -> BulkAddContactsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Bulk add contacts to a campaign using filter criteria.

Instead of passing individual contact IDs, pass filter criteria:
- `tags`: Filter by contact tags (with `tagMode` for ANY/ALL matching)
- `company`: Filter by company name (exact match)
- `search`: Full-text search across name, company, occupation, email

This allows adding thousands of contacts in a single request efficiently.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif, BulkContactFilter
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.campaigns.bulk_add_campaign_contacts(
    campaign_id="campaignId",
    filter=BulkContactFilter(),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**campaign_id:** `str` — Campaign ID
    
</dd>
</dl>

<dl>
<dd>

**filter:** `BulkContactFilter` — Filter criteria to select which contacts to add
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.campaigns.<a href="src/talkif/campaigns/client.py">bulk_remove_campaign_contacts</a>(...) -> BulkRemoveContactsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Bulk remove contacts from a campaign using the same filter criteria as bulk add.

Contacts that already have a call record, or that are sitting in an active
queue slot, are never removed — the response reports `matched` and `removed`
separately so a partial removal is visible rather than silent.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif, BulkContactFilter
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.campaigns.bulk_remove_campaign_contacts(
    campaign_id="campaignId",
    filter=BulkContactFilter(),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**campaign_id:** `str` — Campaign ID
    
</dd>
</dl>

<dl>
<dd>

**filter:** `BulkContactFilter` — Filter criteria to select which contacts to remove
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.campaigns.<a href="src/talkif/campaigns/client.py">skip_campaign_contact</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Mark a campaign contact as skipped (e.g., DNC, opt-out, manual skip).
The contact will be excluded from future claiming and calling.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.campaigns.skip_campaign_contact(
    campaign_id="campaignId",
    contact_id="contactId",
    reason="manual",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**campaign_id:** `str` — Campaign ID
    
</dd>
</dl>

<dl>
<dd>

**contact_id:** `str` — Campaign contact ID
    
</dd>
</dl>

<dl>
<dd>

**reason:** `str` — Reason for skipping (e.g. "manual", "opt_out", "dnc_list")
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.campaigns.<a href="src/talkif/campaigns/client.py">pause_campaign</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initiates the draining process for a running campaign:
- Status changes to Draining (stops feeding new contacts to queue)
- Active calls are allowed to complete naturally
- When active_calls_count reaches 0, status transitions to Paused
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.campaigns.pause_campaign(
    campaign_id="campaignId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**campaign_id:** `str` — Campaign ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.campaigns.<a href="src/talkif/campaigns/client.py">restart_campaign</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Restarts a campaign for non-called contacts. Resets failed/pending/not-called
contacts back to pending and starts the campaign from Paused/Completed/Cancelled state.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.campaigns.restart_campaign(
    campaign_id="campaignId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**campaign_id:** `str` — Campaign ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.campaigns.<a href="src/talkif/campaigns/client.py">resume_campaign</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Resumes a paused campaign, transitioning it back to Running state.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.campaigns.resume_campaign(
    campaign_id="campaignId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**campaign_id:** `str` — Campaign ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.campaigns.<a href="src/talkif/campaigns/client.py">start_campaign</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.campaigns.start_campaign(
    campaign_id="campaignId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**campaign_id:** `str` — Campaign ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Analytics
<details><summary><code>client.analytics.<a href="src/talkif/analytics/client.py">get_campaign_analytics</a>(...) -> CampaignAnalyticsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get deep analytics for a single campaign.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.analytics.get_campaign_analytics(
    campaign_id="campaignId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**campaign_id:** `str` — Campaign ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.analytics.<a href="src/talkif/analytics/client.py">get_flow_stats</a>(...) -> FlowStatsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get statistics for a specific flow.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.analytics.get_flow_stats(
    flow_id="flowId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**flow_id:** `str` — Flow ID
    
</dd>
</dl>

<dl>
<dd>

**period:** `typing.Optional[TimePeriod]` — Time period
    
</dd>
</dl>

<dl>
<dd>

**start_date:** `typing.Optional[str]` — Start date for custom period
    
</dd>
</dl>

<dl>
<dd>

**end_date:** `typing.Optional[str]` — End date for custom period
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Contacts
<details><summary><code>client.contacts.<a href="src/talkif/contacts/client.py">list_contacts</a>(...) -> ContactListResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.contacts.list_contacts()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `typing.Optional[int]` — Max items to return (1-100)
    
</dd>
</dl>

<dl>
<dd>

**offset:** `typing.Optional[int]` — Items to skip
    
</dd>
</dl>

<dl>
<dd>

**search:** `typing.Optional[str]` — Search by name, phone, or email
    
</dd>
</dl>

<dl>
<dd>

**tag:** `typing.Optional[str]` — Filter by single tag (deprecated, use tags)
    
</dd>
</dl>

<dl>
<dd>

**tags:** `typing.Optional[str]` — Comma-separated tags to filter by
    
</dd>
</dl>

<dl>
<dd>

**tag_mode:** `typing.Optional[str]` — Tag match mode: 'any' (OR) or 'all' (AND)
    
</dd>
</dl>

<dl>
<dd>

**company:** `typing.Optional[str]` — Filter by company
    
</dd>
</dl>

<dl>
<dd>

**include_deleted:** `typing.Optional[bool]` — Include soft-deleted contacts
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.contacts.<a href="src/talkif/contacts/client.py">create_contact</a>(...) -> Contact</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.contacts.create_contact(
    name="Jane Smith",
    primary_phone="+15551234567",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `CreateContactRequest` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.contacts.<a href="src/talkif/contacts/client.py">export_contacts</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.contacts.export_contacts(
    format="format",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**format:** `str` — Export format: csv, json, or vcf
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.contacts.<a href="src/talkif/contacts/client.py">import_contacts</a>(...) -> ImportResult</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.contacts.import_contacts(
    file_content="Sm9obiBEb2UsKzE1NTUxMjM0NTY3",
    format="vcf",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**file_content:** `str` — Base64-encoded file content (VCF, CSV, or JSON)
    
</dd>
</dl>

<dl>
<dd>

**format:** `ImportFormat` — File format of the encoded content
    
</dd>
</dl>

<dl>
<dd>

**confirmed:** `typing.Optional[bool]` — Set to true to execute the import; false returns a dry-run preview
    
</dd>
</dl>

<dl>
<dd>

**default_country_code:** `typing.Optional[str]` — Default country code for phone numbers without + prefix
    
</dd>
</dl>

<dl>
<dd>

**duplicate_strategy:** `typing.Optional[DuplicateStrategy]` — How to handle contacts whose phone number already exists (default: skip)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.contacts.<a href="src/talkif/contacts/client.py">search_by_phone</a>(...) -> ContactSearchResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.contacts.search_by_phone(
    phone="phone",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**phone:** `str` — Phone number to search (E.164 format)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.contacts.<a href="src/talkif/contacts/client.py">list_tags</a>() -> TagsListResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.contacts.list_tags()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.contacts.<a href="src/talkif/contacts/client.py">get_contact</a>(...) -> Contact</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.contacts.get_contact(
    contact_id="contactId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**contact_id:** `str` — Contact ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.contacts.<a href="src/talkif/contacts/client.py">update_contact</a>(...) -> Contact</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.contacts.update_contact(
    contact_id="contactId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**contact_id:** `str` — Contact ID
    
</dd>
</dl>

<dl>
<dd>

**address:** `typing.Optional[ContactAddress]` 
    
</dd>
</dl>

<dl>
<dd>

**company:** `typing.Optional[str]` — Company or organization name
    
</dd>
</dl>

<dl>
<dd>

**email:** `typing.Optional[str]` — Email address
    
</dd>
</dl>

<dl>
<dd>

**interests:** `typing.Optional[typing.List[str]]` — Contact interests or topics (max 50)
    
</dd>
</dl>

<dl>
<dd>

**language:** `typing.Optional[str]` — BCP 47 language code (2-10 characters)
    
</dd>
</dl>

<dl>
<dd>

**name:** `typing.Optional[str]` — Full name of the contact (1-255 characters)
    
</dd>
</dl>

<dl>
<dd>

**notes:** `typing.Optional[str]` — Free-text notes (max 5000 characters)
    
</dd>
</dl>

<dl>
<dd>

**occupation:** `typing.Optional[str]` — Job title or occupation
    
</dd>
</dl>

<dl>
<dd>

**primary_phone:** `typing.Optional[str]` — Primary phone number in E.164 format
    
</dd>
</dl>

<dl>
<dd>

**secondary_phones:** `typing.Optional[typing.List[str]]` — Additional phone numbers in E.164 format (max 10)
    
</dd>
</dl>

<dl>
<dd>

**tags:** `typing.Optional[typing.List[str]]` — Tags for categorization (max 50)
    
</dd>
</dl>

<dl>
<dd>

**timezone:** `typing.Optional[str]` — IANA timezone identifier
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.contacts.<a href="src/talkif/contacts/client.py">delete_contact</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.contacts.delete_contact(
    contact_id="contactId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**contact_id:** `str` — Contact ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.contacts.<a href="src/talkif/contacts/client.py">get_contact_calls</a>(...) -> CallListResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.contacts.get_contact_calls(
    contact_id="contactId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**contact_id:** `str` — Contact ID
    
</dd>
</dl>

<dl>
<dd>

**limit:** `typing.Optional[int]` — Max calls (1-100, default 20)
    
</dd>
</dl>

<dl>
<dd>

**offset:** `typing.Optional[int]` — Pagination offset
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.contacts.<a href="src/talkif/contacts/client.py">restore_contact</a>(...) -> Contact</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.contacts.restore_contact(
    contact_id="contactId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**contact_id:** `str` — Contact ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.contacts.<a href="src/talkif/contacts/client.py">add_tags</a>(...) -> Contact</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.contacts.add_tags(
    contact_id="contactId",
    tags=[
        "vip",
        "priority"
    ],
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**contact_id:** `str` — Contact ID
    
</dd>
</dl>

<dl>
<dd>

**tags:** `typing.List[str]` — Tags to add to the contact (1-50 tags)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.contacts.<a href="src/talkif/contacts/client.py">remove_tags</a>(...) -> Contact</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.contacts.remove_tags(
    contact_id="contactId",
    tags=[
        "vip"
    ],
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**contact_id:** `str` — Contact ID
    
</dd>
</dl>

<dl>
<dd>

**tags:** `typing.List[str]` — Tags to remove from the contact (1-50 tags)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Do Not Call
<details><summary><code>client.do_not_call.<a href="src/talkif/do_not_call/client.py">list_dnc_entries</a>(...) -> DncListResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List DNC entries for an account with pagination.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.do_not_call.list_dnc_entries()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `typing.Optional[int]` — Max items to return (default: 20)
    
</dd>
</dl>

<dl>
<dd>

**offset:** `typing.Optional[int]` — Items to skip
    
</dd>
</dl>

<dl>
<dd>

**search:** `typing.Optional[str]` — Filter by phone number (partial match)
    
</dd>
</dl>

<dl>
<dd>

**source:** `typing.Optional[str]` — Filter by source (exact match)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.do_not_call.<a href="src/talkif/do_not_call/client.py">add_dnc_entry</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Add a phone number to the DNC list.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.do_not_call.add_dnc_entry(
    phone_number="+15551234567",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**phone_number:** `str` — Phone number in E.164 format
    
</dd>
</dl>

<dl>
<dd>

**reason:** `typing.Optional[str]` — Human-readable reason for adding to DNC list (max 500 characters)
    
</dd>
</dl>

<dl>
<dd>

**source:** `typing.Optional[DncSource]` — How this DNC entry was created (default: manual)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.do_not_call.<a href="src/talkif/do_not_call/client.py">bulk_import_dnc</a>(...) -> BulkDncImportResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Bulk import phone numbers to the DNC list.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.do_not_call.bulk_import_dnc(
    phone_numbers=[
        "+15551234567",
        "+15559876543"
    ],
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**phone_numbers:** `typing.List[str]` — Phone numbers in E.164 format (1-10,000 numbers per request)
    
</dd>
</dl>

<dl>
<dd>

**reason:** `typing.Optional[str]` — Human-readable reason applied to all entries (max 500 characters)
    
</dd>
</dl>

<dl>
<dd>

**source:** `typing.Optional[DncSource]` — How these DNC entries were created (default: bulk_import)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.do_not_call.<a href="src/talkif/do_not_call/client.py">check_dnc_status</a>(...) -> CheckDncResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Check if phone numbers are on the DNC list.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.do_not_call.check_dnc_status(
    phone_numbers=[
        "+15551234567",
        "+15559876543"
    ],
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**phone_numbers:** `typing.List[str]` — Phone numbers to check in E.164 format (1-100 numbers per request)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.do_not_call.<a href="src/talkif/do_not_call/client.py">remove_dnc_entry</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Remove a phone number from the DNC list.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.do_not_call.remove_dnc_entry(
    phone_number="phoneNumber",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**phone_number:** `str` — Phone number to remove (URL-encoded E.164)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Errors
<details><summary><code>client.errors.<a href="src/talkif/errors/client.py">error_catalog</a>() -> ErrorCatalogResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all API error codes and field validation codes with descriptions, HTTP status codes, and categories. Use this to build error reference documentation or implement client-side error handling.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.errors.error_catalog()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Flow Functions
<details><summary><code>client.flow_functions.<a href="src/talkif/flow_functions/client.py">list_flow_functions</a>(...) -> PaginatedResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/flow-functions
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.flow_functions.list_flow_functions()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `typing.Optional[int]` — Page size
    
</dd>
</dl>

<dl>
<dd>

**offset:** `typing.Optional[int]` — Page offset
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.flow_functions.<a href="src/talkif/flow_functions/client.py">create_flow_function</a>(...) -> FlowFunctionResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

POST /api/v1/flow-functions
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif, RequestSchema
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.flow_functions.create_flow_function(
    description="Create a new customer order",
    name="create_order",
    request=RequestSchema(
        method="POST",
        url="https://api.example.com/orders/{orderId}",
    ),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**description:** `str` — Description of what the function does (1-1000 characters)
    
</dd>
</dl>

<dl>
<dd>

**name:** `str` — Display name (1-255 characters)
    
</dd>
</dl>

<dl>
<dd>

**request:** `RequestSchema` 

Structured HTTP request: method, url, pathParams, queryParams, body.
See [`RequestSchema`] for shape.
    
</dd>
</dl>

<dl>
<dd>

**param_bindings:** `typing.Optional[typing.Dict[str, typing.Any]]` 

Per-parameter source bindings keyed by flat param name. Optional —
defaults to empty `{}` (all parameters are LLM-extracted). Keys must
match a property name in `request.pathParams`, `request.queryParams`,
or `request.body`. Values:
- `{ "source": "llm" }` — LLM extracts from conversation
- `{ "source": "call_context", "contextKey": "caller.contact_id", "onNull": "reject" }`
- `{ "source": "static", "value": "2026-01" }`
    
</dd>
</dl>

<dl>
<dd>

**timeout_ms:** `typing.Optional[int]` — Timeout in milliseconds (100-30000)
    
</dd>
</dl>

<dl>
<dd>

**webhook_headers:** `typing.Optional[typing.Dict[str, typing.Any]]` — Headers to send with the webhook (encrypted at rest). Write-only.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.flow_functions.<a href="src/talkif/flow_functions/client.py">get_flow_function</a>(...) -> FlowFunctionResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/flow-functions/{id}
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.flow_functions.get_flow_function(
    id="id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.flow_functions.<a href="src/talkif/flow_functions/client.py">update_flow_function</a>(...) -> FlowFunctionResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

PUT /api/v1/flow-functions/{id}
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.flow_functions.update_flow_function(
    id="id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Updated description (1-1000 characters)
    
</dd>
</dl>

<dl>
<dd>

**is_active:** `typing.Optional[bool]` — Updated active status
    
</dd>
</dl>

<dl>
<dd>

**name:** `typing.Optional[str]` — Updated display name (1-255 characters)
    
</dd>
</dl>

<dl>
<dd>

**param_bindings:** `typing.Optional[typing.Dict[str, typing.Any]]` 

Updated per-parameter bindings. Omit to keep existing; `{}` to clear to
all-LLM behavior; object to replace.
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[RequestSchema]` 
    
</dd>
</dl>

<dl>
<dd>

**timeout_ms:** `typing.Optional[int]` — Updated timeout in milliseconds (100-30000)
    
</dd>
</dl>

<dl>
<dd>

**webhook_headers:** `typing.Optional[typing.Dict[str, typing.Any]]` — Updated headers (encrypted at rest). Pass null to clear, omit to keep existing.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.flow_functions.<a href="src/talkif/flow_functions/client.py">delete_flow_function</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

DELETE /api/v1/flow-functions/{id}
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.flow_functions.delete_flow_function(
    id="id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Flow Templates
<details><summary><code>client.flow_templates.<a href="src/talkif/flow_templates/client.py">list_system_templates</a>(...) -> PaginatedResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/flow-templates
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.flow_templates.list_system_templates()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**category:** `typing.Optional[str]` — Filter by category
    
</dd>
</dl>

<dl>
<dd>

**limit:** `typing.Optional[int]` — Page size
    
</dd>
</dl>

<dl>
<dd>

**offset:** `typing.Optional[int]` — Page offset
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.flow_templates.<a href="src/talkif/flow_templates/client.py">get_flow_template</a>(...) -> FlowTemplate</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/flow-templates/:slug

Note: This is a public endpoint that doesn't require auth, but if the user is logged in,
they can also see their account-specific templates
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.flow_templates.get_flow_template(
    slug="slug",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**slug:** `str` — Template slug
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.flow_templates.<a href="src/talkif/flow_templates/client.py">instantiate_template</a>(...) -> typing.Dict[str, typing.Any]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

POST /api/v1/flows/from-template/:templateSlug
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.flow_templates.instantiate_template(
    template_slug="templateSlug",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**template_slug:** `str` — Template slug
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Optional description override
    
</dd>
</dl>

<dl>
<dd>

**name:** `typing.Optional[str]` — Optional name override (defaults to template name)
    
</dd>
</dl>

<dl>
<dd>

**variables:** `typing.Optional[typing.Dict[str, typing.Any]]` — Variable replacements for template placeholders
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Flows
<details><summary><code>client.flows.<a href="src/talkif/flows/client.py">list_flows</a>() -> PaginatedResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/flows

Returns lightweight flow list with connected phones.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.flows.list_flows()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.flows.<a href="src/talkif/flows/client.py">create_flow</a>(...) -> FlowDetailResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

POST /api/v1/flows

Definition is optional — omit to create an empty draft for the builder UI,
or provide it to create a flow with initial content.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.flows.create_flow(
    name="Appointment Reminder",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**name:** `str` — Display name of the flow (1-255 characters)
    
</dd>
</dl>

<dl>
<dd>

**analysis_instructions:** `typing.Optional[str]` — Custom analysis instructions appended to the base analysis prompt
    
</dd>
</dl>

<dl>
<dd>

**analysis_override:** `typing.Optional[str]` — Call analysis behavior override: "use_account_default", "enabled", or "disabled"
    
</dd>
</dl>

<dl>
<dd>

**definition:** `typing.Optional[FlowDefinition]` 
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Description of the flow's purpose (max 1000 characters)
    
</dd>
</dl>

<dl>
<dd>

**layout:** `typing.Optional[typing.Dict[str, typing.Any]]` — Visual builder layout (node positions, viewport). Opaque to the API; stored and returned as-is.
    
</dd>
</dl>

<dl>
<dd>

**max_call_duration:** `typing.Optional[MaxCallDurationSettings]` 
    
</dd>
</dl>

<dl>
<dd>

**recording_override:** `typing.Optional[str]` — Recording behavior override: "use_account_default", "enabled", or "disabled"
    
</dd>
</dl>

<dl>
<dd>

**user_idle:** `typing.Optional[UserIdleSettings]` 
    
</dd>
</dl>

<dl>
<dd>

**voicemail_enabled:** `typing.Optional[bool]` — Enable voicemail detection for this flow (outbound Twilio calls only)
    
</dd>
</dl>

<dl>
<dd>

**voicemail_message:** `typing.Optional[str]` — Static voicemail message spoken verbatim (skips the composer LLM call)
    
</dd>
</dl>

<dl>
<dd>

**voicemail_message_prompt:** `typing.Optional[str]` — Instruction for composing the voicemail message (ignored if message is set)
    
</dd>
</dl>

<dl>
<dd>

**voicemail_response_delay_secs:** `typing.Optional[float]` — Seconds to wait after the callee stops speaking before leaving the message
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.flows.<a href="src/talkif/flows/client.py">get_flow</a>(...) -> FlowDetailResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/flows/:flowId

Returns full flow details including definition, layout, and connected phones.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.flows.get_flow(
    flow_id="flowId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**flow_id:** `str` — Flow ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.flows.<a href="src/talkif/flows/client.py">update_flow</a>(...) -> FlowDetailResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

PUT /api/v1/flows/:flowId
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.flows.update_flow(
    flow_id="flowId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**flow_id:** `str` — Flow ID
    
</dd>
</dl>

<dl>
<dd>

**analysis_instructions:** `typing.Optional[str]` — Custom analysis instructions appended to the base analysis prompt
    
</dd>
</dl>

<dl>
<dd>

**analysis_override:** `typing.Optional[str]` — Call analysis behavior override: "use_account_default", "enabled", or "disabled"
    
</dd>
</dl>

<dl>
<dd>

**definition:** `typing.Optional[FlowDefinition]` 
    
</dd>
</dl>

<dl>
<dd>

**description:** `typing.Optional[str]` — Updated description (max 1000 characters)
    
</dd>
</dl>

<dl>
<dd>

**layout:** `typing.Optional[typing.Dict[str, typing.Any]]` — Visual builder layout. Opaque to the API; stored and returned as-is.
    
</dd>
</dl>

<dl>
<dd>

**max_call_duration:** `typing.Optional[MaxCallDurationSettings]` 
    
</dd>
</dl>

<dl>
<dd>

**name:** `typing.Optional[str]` — Updated display name (1-255 characters)
    
</dd>
</dl>

<dl>
<dd>

**recording_override:** `typing.Optional[str]` — Recording behavior override: "use_account_default", "enabled", or "disabled"
    
</dd>
</dl>

<dl>
<dd>

**tags:** `typing.Optional[typing.List[str]]` — Updated tags for filtering and organization (max 10)
    
</dd>
</dl>

<dl>
<dd>

**user_idle:** `typing.Optional[UserIdleSettings]` 
    
</dd>
</dl>

<dl>
<dd>

**voicemail_enabled:** `typing.Optional[bool]` — Enable voicemail detection for this flow (outbound Twilio calls only)
    
</dd>
</dl>

<dl>
<dd>

**voicemail_message:** `typing.Optional[str]` — Static voicemail message spoken verbatim (skips the composer LLM call)
    
</dd>
</dl>

<dl>
<dd>

**voicemail_message_prompt:** `typing.Optional[str]` — Instruction for composing the voicemail message (ignored if message is set)
    
</dd>
</dl>

<dl>
<dd>

**voicemail_response_delay_secs:** `typing.Optional[float]` — Seconds to wait after the callee stops speaking before leaving the message
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.flows.<a href="src/talkif/flows/client.py">delete_flow</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

DELETE /api/v1/flows/:flowId

Returns 204 No Content on success.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.flows.delete_flow(
    flow_id="flowId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**flow_id:** `str` — Flow ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.flows.<a href="src/talkif/flows/client.py">publish_flow</a>(...) -> PublishFlowResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

POST /api/v1/flows/:flowId/publish
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.flows.publish_flow(
    flow_id="flowId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**flow_id:** `str` — Flow ID
    
</dd>
</dl>

<dl>
<dd>

**expected_version:** `typing.Optional[str]` — Expected current version for optimistic locking (rejects with 409 if stale)
    
</dd>
</dl>

<dl>
<dd>

**notes:** `typing.Optional[str]` — Changelog notes describing what changed in this version (max 1000 characters)
    
</dd>
</dl>

<dl>
<dd>

**version:** `typing.Optional[str]` — Explicit version override in X.Y.Z format (auto-increments patch if omitted)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.flows.<a href="src/talkif/flows/client.py">rollback_flow</a>(...) -> RollbackResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

POST /api/v1/flows/:flowId/rollback/:version
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.flows.rollback_flow(
    flow_id="flowId",
    version="version",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**flow_id:** `str` — Flow ID
    
</dd>
</dl>

<dl>
<dd>

**version:** `str` — Version to rollback to
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.flows.<a href="src/talkif/flows/client.py">validate_flow</a>(...) -> ValidationResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

POST /api/v1/flows/:flowId/validate
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.flows.validate_flow(
    flow_id="flowId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**flow_id:** `str` — Flow ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.flows.<a href="src/talkif/flows/client.py">get_flow_version</a>(...) -> FlowVersionDetailResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/flows/:flowId/versions/:version
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.flows.get_flow_version(
    flow_id="flowId",
    version="version",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**flow_id:** `str` — Flow ID
    
</dd>
</dl>

<dl>
<dd>

**version:** `str` — Version string
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## AI Models
<details><summary><code>client.ai_models.<a href="src/talkif/ai_models/client.py">list_providers_public</a>(...) -> FlowProvidersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/models
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.ai_models.list_providers_public()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**use_case:** `typing.Optional[str]` — Filter by use case
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.ai_models.<a href="src/talkif/ai_models/client.py">list_tts_voices</a>(...) -> VoicesDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/models/tts/voices

When any of gender, age, language, accent, or sort are present, routes to
the ElevenLabs /v1/shared-voices endpoint (rich filtering, offset pagination).
Otherwise routes to /v2/voices (simpler, cursor pagination).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.ai_models.list_tts_voices()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page_size:** `typing.Optional[int]` — Page size (max 100, default 50)
    
</dd>
</dl>

<dl>
<dd>

**next_page_token:** `typing.Optional[str]` — Pagination token for next page
    
</dd>
</dl>

<dl>
<dd>

**search:** `typing.Optional[str]` — Search term
    
</dd>
</dl>

<dl>
<dd>

**voice_type:** `typing.Optional[str]` — Voice type filter (v2 API)
    
</dd>
</dl>

<dl>
<dd>

**category:** `typing.Optional[str]` — Category filter
    
</dd>
</dl>

<dl>
<dd>

**gender:** `typing.Optional[str]` — Gender filter (male, female, neutral) — shared-voices API
    
</dd>
</dl>

<dl>
<dd>

**age:** `typing.Optional[str]` — Age group filter (young, middle_aged, old) — shared-voices API
    
</dd>
</dl>

<dl>
<dd>

**language:** `typing.Optional[str]` — Language filter (ISO code) — shared-voices API
    
</dd>
</dl>

<dl>
<dd>

**accent:** `typing.Optional[str]` — Accent filter — shared-voices API
    
</dd>
</dl>

<dl>
<dd>

**sort:** `typing.Optional[str]` — Sort order (trending, latest, most_users) — shared-voices API
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — 0-based page offset — shared-voices API
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Phone Numbers
<details><summary><code>client.phone_numbers.<a href="src/talkif/phone_numbers/client.py">list_phone_numbers</a>(...) -> typing.List[PhoneNumberResponse]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/phone/numbers
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.phone_numbers.list_phone_numbers()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `typing.Optional[int]` — Max items to return
    
</dd>
</dl>

<dl>
<dd>

**offset:** `typing.Optional[int]` — Items to skip
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.phone_numbers.<a href="src/talkif/phone_numbers/client.py">list_available_numbers</a>(...) -> typing.List[AvailablePhoneNumber]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/phone/numbers/twilio/available

Query Parameters:
- `providerId` (required): Provider ID
- `countryCode` (required): ISO country code (e.g., "US", "GB")
- `numberType` (optional): "local", "toll_free", or "mobile" (default: "local")
- `areaCode` (optional): Area code filter (US/Canada only)
- `contains` (optional): Pattern to match (supports wildcards: *, %)
- `inPostalCode` (optional): Filter by postal/ZIP code
- `inRegion` (optional): Filter by state/region
- `inRateCenter` (optional): Filter by rate center
- `inLata` (optional): Filter by LATA
- `inLocality` (optional): Filter by city
- `nearNumber` (optional): Find numbers near this phone number
- `nearLatLong` (optional): Find numbers near lat,long
- `distance` (optional): Radius in miles (default: 25, max: 500)
- `smsEnabled` (optional): Filter SMS-capable numbers
- `mmsEnabled` (optional): Filter MMS-capable numbers
- `voiceEnabled` (optional): Filter voice-capable numbers
- `faxEnabled` (optional): Filter fax-capable numbers
- `beta` (optional): Filter beta numbers
- `excludeAllAddressRequired` (optional): Exclude numbers requiring any address
- `excludeLocalAddressRequired` (optional): Exclude numbers requiring local address
- `excludeForeignAddressRequired` (optional): Exclude numbers requiring foreign address
- `limit` (optional): Max results (default: 20, max: 1000)
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.phone_numbers.list_available_numbers(
    provider_id="providerId",
    country_code="countryCode",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**provider_id:** `str` — Provider ID
    
</dd>
</dl>

<dl>
<dd>

**country_code:** `str` — ISO country code (e.g., US, GB)
    
</dd>
</dl>

<dl>
<dd>

**number_type:** `typing.Optional[str]` — Number type: local, toll_free, or mobile
    
</dd>
</dl>

<dl>
<dd>

**area_code:** `typing.Optional[str]` — Area code filter (US/Canada only)
    
</dd>
</dl>

<dl>
<dd>

**contains:** `typing.Optional[str]` — Pattern to match in the phone number
    
</dd>
</dl>

<dl>
<dd>

**limit:** `typing.Optional[int]` — Max results (default: 20, max: 1000)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.phone_numbers.<a href="src/talkif/phone_numbers/client.py">list_available_countries</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/phone/numbers/twilio/available-countries
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.phone_numbers.list_available_countries(
    provider_id="providerId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**provider_id:** `str` — Provider ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.phone_numbers.<a href="src/talkif/phone_numbers/client.py">get_pricing</a>(...) -> PhoneNumberPricing</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/phone/numbers/twilio/pricing
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.phone_numbers.get_pricing(
    provider_id="providerId",
    country_code="countryCode",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**provider_id:** `str` — Provider ID
    
</dd>
</dl>

<dl>
<dd>

**country_code:** `str` — ISO country code
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.phone_numbers.<a href="src/talkif/phone_numbers/client.py">purchase_phone_number</a>(...) -> PhoneNumberResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

POST /api/v1/phone/numbers/twilio/purchase
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.phone_numbers.purchase_phone_number(
    phone_number="+15551234567",
    provider_id="550e8400-e29b-41d4-a716-446655440000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**phone_number:** `str` — Phone number to purchase in E.164 format
    
</dd>
</dl>

<dl>
<dd>

**provider_id:** `str` — ID of the provider to purchase through
    
</dd>
</dl>

<dl>
<dd>

**friendly_name:** `typing.Optional[str]` — Optional friendly name for the number
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.phone_numbers.<a href="src/talkif/phone_numbers/client.py">get_phone_number</a>(...) -> PhoneNumberResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/phone/numbers/:id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.phone_numbers.get_phone_number(
    id="id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — Phone number ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.phone_numbers.<a href="src/talkif/phone_numbers/client.py">update_phone_number</a>(...) -> PhoneNumberResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

PUT /api/v1/phone/numbers/:id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.phone_numbers.update_phone_number(
    id="id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — Phone number ID
    
</dd>
</dl>

<dl>
<dd>

**friendly_name:** `typing.Optional[str]` — Updated friendly name for the number
    
</dd>
</dl>

<dl>
<dd>

**recording_override:** `typing.Optional[str]` — Recording override setting (e.g. "do-not-record", "record-from-answer")
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.phone_numbers.<a href="src/talkif/phone_numbers/client.py">release_phone_number</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

DELETE /api/v1/phone/numbers/:id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.phone_numbers.release_phone_number(
    id="id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — Phone number ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.phone_numbers.<a href="src/talkif/phone_numbers/client.py">connect_flow</a>(...) -> PhoneNumberResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

PATCH /api/v1/phone/numbers/:phoneNumberId/connect-flow
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.phone_numbers.connect_flow(
    phone_number_id="phoneNumberId",
    flow_id="550e8400-e29b-41d4-a716-446655440000",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**phone_number_id:** `str` — Phone number ID
    
</dd>
</dl>

<dl>
<dd>

**flow_id:** `str` — ID of the flow to connect to this phone number
    
</dd>
</dl>

<dl>
<dd>

**flow_version:** `typing.Optional[str]` — Optional specific flow version to use
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.phone_numbers.<a href="src/talkif/phone_numbers/client.py">disconnect_flow</a>(...) -> PhoneNumberResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

PATCH /api/v1/phone/numbers/:phoneNumberId/disconnect-flow
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.phone_numbers.disconnect_flow(
    phone_number_id="phoneNumberId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**phone_number_id:** `str` — Phone number ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Phone Providers
<details><summary><code>client.phone_providers.<a href="src/talkif/phone_providers/client.py">list_phone_providers</a>(...) -> typing.List[PhoneProviderResponse]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/phone/providers
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.phone_providers.list_phone_providers()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `typing.Optional[int]` — Max items to return
    
</dd>
</dl>

<dl>
<dd>

**offset:** `typing.Optional[int]` — Items to skip
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.phone_providers.<a href="src/talkif/phone_providers/client.py">get_provider</a>(...) -> PhoneProviderResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/phone/providers/:id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.phone_providers.get_provider(
    id="id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `str` — Provider ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## PublicCalls
<details><summary><code>client.public_calls.<a href="src/talkif/public_calls/client.py">create_call</a>() -> CreateWebRtcCallResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

POST /api/v1/public/calls/calls
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.public_calls.create_call()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.public_calls.<a href="src/talkif/public_calls/client.py">get_call_status</a>(...) -> PublicCallStatusResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/public/calls/calls/{callId}
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.public_calls.get_call_status(
    call_id="callId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**call_id:** `str` — Call ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.public_calls.<a href="src/talkif/public_calls/client.py">relay_offer</a>(...) -> WebRtcOfferResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

POST /api/v1/public/calls/calls/{callId}/offer
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.public_calls.relay_offer(
    call_id="callId",
    sdp="v=0\r\no=- 0 0 IN IP4 127.0.0.1\r\n...",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**call_id:** `str` — Call ID
    
</dd>
</dl>

<dl>
<dd>

**sdp:** `str` — WebRTC SDP offer string
    
</dd>
</dl>

<dl>
<dd>

**ice_servers:** `typing.Optional[typing.List[IceServerEntry]]` — ICE servers to forward to the bot for WebRTC connection
    
</dd>
</dl>

<dl>
<dd>

**use_smart_turn:** `typing.Optional[bool]` — Whether to use smart TURN server selection
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.public_calls.<a href="src/talkif/public_calls/client.py">get_ice_servers</a>() -> IceServersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET /api/v1/public/calls/ice-servers
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.public_calls.get_ice_servers()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.public_calls.<a href="src/talkif/public_calls/client.py">create_session</a>(...) -> CreatePublicSessionResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

POST /api/v1/public/calls/session
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.public_calls.create_session(
    publishable_key="pk_live_AbCdEf123456",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**publishable_key:** `str` — Publishable key from the flow's public-access config
    
</dd>
</dl>

<dl>
<dd>

**turnstile_token:** `typing.Optional[str]` — Cloudflare Turnstile token (required once the bot gate is active)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Schedules
<details><summary><code>client.schedules.<a href="src/talkif/schedules/client.py">list_schedules</a>(...) -> ScheduleListResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.schedules.list_schedules()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**status:** `typing.Optional[ScheduleStatus]` — Filter by status
    
</dd>
</dl>

<dl>
<dd>

**limit:** `typing.Optional[int]` — Max items to return
    
</dd>
</dl>

<dl>
<dd>

**offset:** `typing.Optional[int]` — Items to skip
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.schedules.<a href="src/talkif/schedules/client.py">create_schedule</a>(...) -> ScheduleResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.schedules.create_schedule(
    contact_id="550e8400-e29b-41d4-a716-446655440000",
    flow_id="550e8400-e29b-41d4-a716-446655440000",
    frequency="once",
    from_phone_number="+15551234567",
    name="Daily Follow-up Call",
    provider_id="550e8400-e29b-41d4-a716-446655440000",
    schedule_time="09:00",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**contact_id:** `str` — Contact to call on each schedule execution
    
</dd>
</dl>

<dl>
<dd>

**flow_id:** `str` — Flow (conversation script) to use for the call
    
</dd>
</dl>

<dl>
<dd>

**frequency:** `ScheduleFrequency` — How often the schedule should repeat
    
</dd>
</dl>

<dl>
<dd>

**from_phone_number:** `str` — Caller ID phone number in E.164 format
    
</dd>
</dl>

<dl>
<dd>

**name:** `str` — Human-readable name for the schedule
    
</dd>
</dl>

<dl>
<dd>

**provider_id:** `str` — VoIP provider to route the call through
    
</dd>
</dl>

<dl>
<dd>

**schedule_time:** `str` — Time of day to execute in HH:MM or HH:MM:SS format
    
</dd>
</dl>

<dl>
<dd>

**cron_expression:** `typing.Optional[str]` — Custom cron expression, required when frequency is `custom_cron`
    
</dd>
</dl>

<dl>
<dd>

**day_of_month:** `typing.Optional[int]` — Day of month to run on (1-28), used with `monthly` frequency
    
</dd>
</dl>

<dl>
<dd>

**days_of_week:** `typing.Optional[typing.List[int]]` — Days of week to run on (1=Monday through 7=Sunday), used with `weekly` frequency
    
</dd>
</dl>

<dl>
<dd>

**end_date:** `typing.Optional[datetime.date]` — Date after which the schedule will not execute
    
</dd>
</dl>

<dl>
<dd>

**max_retries:** `typing.Optional[int]` — Maximum number of retry attempts per execution (0-10)
    
</dd>
</dl>

<dl>
<dd>

**max_runs:** `typing.Optional[int]` — Maximum number of executions before auto-completing
    
</dd>
</dl>

<dl>
<dd>

**retry_delay_minutes:** `typing.Optional[int]` — Minutes to wait before retrying a failed call (1-1440)
    
</dd>
</dl>

<dl>
<dd>

**retry_on_failure:** `typing.Optional[bool]` — Whether to retry the call if it fails
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.schedules.<a href="src/talkif/schedules/client.py">get_schedule</a>(...) -> ScheduleResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.schedules.get_schedule(
    schedule_id="scheduleId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**schedule_id:** `str` — Schedule ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.schedules.<a href="src/talkif/schedules/client.py">update_schedule</a>(...) -> ScheduleResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.schedules.update_schedule(
    schedule_id="scheduleId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**schedule_id:** `str` — Schedule ID
    
</dd>
</dl>

<dl>
<dd>

**cron_expression:** `typing.Optional[str]` — Custom cron expression, required when frequency is `custom_cron`
    
</dd>
</dl>

<dl>
<dd>

**day_of_month:** `typing.Optional[int]` — Day of month to run on (1-28)
    
</dd>
</dl>

<dl>
<dd>

**days_of_week:** `typing.Optional[typing.List[int]]` — Days of week to run on (1=Monday through 7=Sunday)
    
</dd>
</dl>

<dl>
<dd>

**end_date:** `typing.Optional[datetime.date]` — Date after which the schedule will not execute
    
</dd>
</dl>

<dl>
<dd>

**frequency:** `typing.Optional[ScheduleFrequency]` 
    
</dd>
</dl>

<dl>
<dd>

**max_retries:** `typing.Optional[int]` — Maximum number of retry attempts per execution (0-10)
    
</dd>
</dl>

<dl>
<dd>

**max_runs:** `typing.Optional[int]` — Maximum number of executions before auto-completing
    
</dd>
</dl>

<dl>
<dd>

**name:** `typing.Optional[str]` — Human-readable name for the schedule
    
</dd>
</dl>

<dl>
<dd>

**retry_delay_minutes:** `typing.Optional[int]` — Minutes to wait before retrying a failed call (1-1440)
    
</dd>
</dl>

<dl>
<dd>

**retry_on_failure:** `typing.Optional[bool]` — Whether to retry the call if it fails
    
</dd>
</dl>

<dl>
<dd>

**schedule_time:** `typing.Optional[str]` — Time of day to execute in HH:MM or HH:MM:SS format
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.schedules.<a href="src/talkif/schedules/client.py">delete_schedule</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.schedules.delete_schedule(
    schedule_id="scheduleId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**schedule_id:** `str` — Schedule ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.schedules.<a href="src/talkif/schedules/client.py">pause_schedule</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.schedules.pause_schedule(
    schedule_id="scheduleId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**schedule_id:** `str` — Schedule ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.schedules.<a href="src/talkif/schedules/client.py">resume_schedule</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from talkif import Talkif
from talkif.environment import TalkifEnvironment

client = Talkif(
    token="<token>",
    environment=TalkifEnvironment.PRODUCTION,
)

client.schedules.resume_schedule(
    schedule_id="scheduleId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**schedule_id:** `str` — Schedule ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

