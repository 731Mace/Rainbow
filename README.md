# Install-Package Sentry -Version 2.1.6          
# using Sentry;

public class MvcApplication : System.Web.HttpApplication
{
    private IDisposable _sentry;

    protected void Application_Start()
    {
        // Add this to Application_Start
        _sentry = SentrySdk.Init(o =>
        {
            o.Dsn = new Dsn("https://examplePublicKey@o0.ingest.sentry.io/0");
        });
    }

    protected void Application_Error()
    {
        var exception = Server.GetLastError();
        SentrySdk.CaptureException(exception);
    }

    protected void Application_End()
    {
        _sentry?.Dispose();
    }
}

import * as Sentry from "@sentry/browser"; import { Integrations } from "@sentry/tracing";

Sentry.init({ dsn: 'https://23e64079f5224914a5711960c4b92596@o468009.ingest.sentry.io/5495295', integrations: [ new Integrations.BrowserTracing(), ],

// We recommend adjusting this value in production, or using tracesSampler // for finer control tracesSampleRate: 1.0, });

C#

Copied
SentrySdk.Init(o =>
{
  UserFactory = new MyUserFactory();
}
