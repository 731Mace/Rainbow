# Install-Package Sentry -Version 2.1.6          
tbc-


Macen Mansfield
import * as Sentry from "@sentry/browser";
import { Integrations } from "@sentry/tracing";

Sentry.init({
  dsn: 'https://23e64079f5224914a5711960c4b92596@o468009.ingest.sentry.io/5495295',
  integrations: [
    new Integrations.BrowserTracing(),
  ],

  // We recommend adjusting this value in production, or using tracesSampler
  // for finer control
  tracesSampleRate: 1.0,
});
