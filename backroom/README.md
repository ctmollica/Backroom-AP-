# Backroom

**Send the quote before your competitor does.**

Backroom is a quoting and follow-up assistant for home trades businesses (plumbing, HVAC, electrical). It turns job details into a professional quote in minutes, then follows up until the customer says yes or no.

## The problem

Owner-operators are on job sites all day, so quotes get written at night or forgotten, and follow-up is inconsistent. Homeowners usually hire the first contractor who sends a clear price, so slow quoting quietly costs real money.

## What's in this repo

| File | What it is |
|---|---|
| `backroom.html` | Marketing landing page with an early-access form |
| `backroom-tool.html` | Quote Builder: the first working version of the product |

Both are single, self-contained HTML files. There is no build step and no dependencies.

## Running it

Open either file in a browser:

```bash
open backroom.html          # macOS
xdg-open backroom-tool.html # Linux
```

Or serve the folder locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000/backroom-tool.html
```

## Quote Builder

1. **The job:** company name, customer name, and a job description.
2. **Price book:** editable list of services and prices (preloaded with sample trades items).
3. **Quote lines:** add from the price book or let "Draft quote from description" match keywords. Edit quantities, prices, and tax.
4. **Preview:** customer-facing quote you can print or save as a PDF.
5. **Send and follow up:** copy-ready texts for the initial send and for day 2, 5, and 10 follow-ups, in a friendly or direct tone.

Quote data and the price book are saved in the browser's `localStorage`. Nothing is sent to a server.

## Known limitations

- The draft step is keyword matching against the price book, not AI.
- Nothing is sent automatically. Messages are copied into a separate texting app.
- Prices in the default price book are placeholders. Replace them with real local rates.
- The early-access form on the landing page shows a confirmation but does not store or send the email address.

## Roadmap

- [ ] AI drafting from call notes and customer photos
- [ ] Price suggestions from past jobs
- [ ] Automatic SMS/email sending and scheduled follow-ups (with consent handling)
- [ ] Customer-facing accept page with deposit payment
- [ ] Hand-off to existing scheduling and invoicing tools (Jobber, Housecall Pro, etc.)
- [ ] Real waitlist backend for the landing page

## Before launch checklist

- [ ] Pick a launch trade and build pricing logic for it
- [ ] Interview 10 owners before building further
- [ ] Check domain and trademark availability for "Backroom"
- [ ] Review SMS consent rules (e.g., TCPA) before sending texts on customers' behalf

## Design

- **Colors:** navy `#14294A`, blue `#0A6CFF`
- **Font:** Outfit (Google Fonts)
- **Logo:** an arrow inside a "B" with speed lines, drawn as inline SVG in both files

## License

TBD
