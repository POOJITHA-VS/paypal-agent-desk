# paypal-agent-desk
# PayPal Agent Desk

An AI billing agent for freelancers and small shops. Describe a job in plain
words, for example "Bill Ravi 3 hrs design at $40 and 2 logos at $75".
Gemini turns it into line items and creates a PayPal sandbox checkout link.
The dashboard then tracks the payment status.

## Problem
Small sellers lose time filling in invoice forms and chasing late payments.

## Features
- Chat to PayPal checkout link (PayPal Orders API, sandbox)
- Payment status tracking, order capture, cancel and refund
- Dashboard with totals, filters and CSV export
- Confirmation required for bills over $500 and for all refunds

## Run it
1. Install Node.js 18 or newer (no npm install needed).
2. Get PayPal sandbox keys: developer.paypal.com > Apps & Credentials > Sandbox.
   Use a United States sandbox Business account for the app.
3. Get a free Gemini key: aistudio.google.com/apikey
4. In a terminal (PowerShell example):

   $env:PAYPAL_CLIENT_ID="your client id"
   $env:PAYPAL_CLIENT_SECRET="your secret"
   $env:GEMINI_API_KEY="your gemini key"
   $env:GEMINI_MODEL="gemini-3.5-flash"
   node server.js

   On Mac/Linux use: export NAME="value"

5. Open http://localhost:3000
6. Click the example, open the payment link, and pay with a sandbox
   Personal (buyer) account. The status turns COMPLETED.

## Tools used
- PayPal Orders API (sandbox): create, get, capture, refund
- Google Gemini (function calling): understands the request and runs the actions

## License
MIT
