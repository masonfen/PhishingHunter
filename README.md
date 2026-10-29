# OVERVIEW
PhishingHunter is a locally hosted, automated workflow that uses AI to determine whether an email is phishing.

It provides a comprehensive analysis of each email and sends a verdict for an analyst to review. Every five minutes, a Splunk alert picks up the oldest untriaged email and sends it to an n8n workflow. Any links are scanned with urlscan.io and VirusTotal, and the evidence they return such as detection counts, impersonated brands, and certificate age, is passed to Gemini along with the email’s sender, reply-to, subject, and body. Gemini returns a verdict (Malicious, Suspicious, or Benign), a confidence level, and the reasoning behind it, which is logged to a dedicated triage index in Splunk.
