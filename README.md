
src/routes/index.tsx
import { createFileRoute } from "@tanstack/react-router";
import { Button } from "@/components/ui/button";
import { Monitor, Zap, Shield, Globe, Check } from "lucide-react";
export const Route = createFileRoute("/")({
  head: () => ({
    meta: [
      { title: "Your App" },
      { name: "description", content: "Replace this with a one-sentence description of your app." },
      { property: "og:title", content: "Your App" },
      { property: "og:description", content: "Replace this with a one-sentence description of your app." },
      { title: "RDPFree — Free Remote Desktop in the Cloud" },
      { name: "description", content: "Spin up a free Windows RDP in seconds. Fast, secure, no credit card required." },
      { property: "og:title", content: "RDPFree — Free Remote Desktop in the Cloud" },
      { property: "og:description", content: "Spin up a free Windows RDP in seconds. Fast, secure, no credit card required." },
    ],
  }),
  component: Index,
});
// IMPORTANT: Replace this placeholder. See ./README.md for routing conventions.
function Index() {
  return (
    <div
      className="flex min-h-screen items-center justify-center"
      style={{ backgroundColor: "#fcfbf8" }}
    >
      <img
        data-lovable-blank-page-placeholder="REMOVE_THIS"
        src="https://cdn.gpteng.co/blank-app-v1.svg"
        alt="Your app will live here!"
      />
    <div className="min-h-screen bg-background text-foreground">
      <header className="border-b border-border/60">
        <div className="mx-auto flex max-w-6xl items-center justify-between px-6 py-5">
          <div className="flex items-center gap-2 font-semibold">
            <Monitor className="h-5 w-5 text-primary" />
            <span>RDPFree</span>
          </div>
          <nav className="hidden gap-8 text-sm text-muted-foreground md:flex">
            <a href="#features" className="hover:text-foreground">Features</a>
            <a href="#pricing" className="hover:text-foreground">Pricing</a>
            <a href="#faq" className="hover:text-foreground">FAQ</a>
          </nav>
          <Button size="sm">Get started</Button>
        </div>
      </header>
      <main>
        <section className="mx-auto max-w-6xl px-6 py-24 text-center">
          <span className="inline-block rounded-full border border-border bg-muted px-3 py-1 text-xs font-medium text-muted-foreground">
            100% free · No credit card
          </span>
          <h1 className="mt-6 text-balance text-5xl font-bold tracking-tight md:text-6xl">
            Free Remote Desktop, ready in seconds
          </h1>
          <p className="mx-auto mt-6 max-w-2xl text-lg text-muted-foreground">
            RDPFree gives you instant access to a Windows cloud desktop from any device.
            Test software, browse safely, or run heavy tasks — without buying a PC.
          </p>
          <div className="mt-10 flex flex-col items-center justify-center gap-3 sm:flex-row">
            <Button size="lg">Launch your free RDP</Button>
            <Button size="lg" variant="outline">See how it works</Button>
          </div>
        </section>
        <section id="features" className="border-t border-border/60 bg-muted/30">
          <div className="mx-auto grid max-w-6xl gap-8 px-6 py-20 md:grid-cols-3">
            {[
              { icon: Zap, title: "Instant access", desc: "Your desktop boots in under 30 seconds — no installs, no setup." },
              { icon: Shield, title: "Secure by default", desc: "Encrypted sessions and isolated environments keep your work private." },
              { icon: Globe, title: "Anywhere, any device", desc: "Connect from Windows, Mac, Linux, iOS, or Android with one click." },
            ].map(({ icon: Icon, title, desc }) => (
              <div key={title} className="rounded-lg border border-border bg-background p-6">
                <Icon className="h-6 w-6 text-primary" />
                <h3 className="mt-4 font-semibold">{title}</h3>
                <p className="mt-2 text-sm text-muted-foreground">{desc}</p>
              </div>
            ))}
          </div>
        </section>
        <section id="pricing" className="mx-auto max-w-3xl px-6 py-24 text-center">
          <h2 className="text-3xl font-bold tracking-tight md:text-4xl">Everything you need, free</h2>
          <ul className="mx-auto mt-8 max-w-md space-y-3 text-left">
            {["Windows cloud desktop", "Fast SSD storage", "1 Gbps network", "Browser-based access", "No credit card required"].map((item) => (
              <li key={item} className="flex items-center gap-3 text-sm">
                <Check className="h-4 w-4 text-primary" />
                {item}
              </li>
            ))}
          </ul>
          <div className="mt-10">
            <Button size="lg">Start your free session</Button>
          </div>
        </section>
      </main>
      <footer className="border-t border-border/60">
        <div className="mx-auto max-w-6xl px-6 py-8 text-sm text-muted-foreground">
          © {new Date().getFullYear()} RDPFree. All rights reserved.
        </div>
      </footer>
    </div>
  );
}
