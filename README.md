import React from "react";
import { motion } from "framer-motion";
import { Button } from "@/components/ui/button";
import { Card, CardContent, CardHeader, CardTitle, CardDescription } from "@/components/ui/card";
import { Input } from "@/components/ui/input";
import { Textarea } from "@/components/ui/textarea";
import { Check, Sparkles, Rocket, Shield, Mail, Phone, MapPin } from "lucide-react";

// --- Simple helpers ---
const fadeUp = {
  initial: { opacity: 0, y: 24 },
  whileInView: { opacity: 1, y: 0 },
  transition: { duration: 0.6 },
  viewport: { once: true, amount: 0.3 },
};

const Section = ({ id, className = "", children }) => (
  <section id={id} className={`max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 ${className}`}>{children}</section>
);

export default function Website() {
  return (
    <div className="min-h-screen bg-gradient-to-b from-indigo-50 via-white to-indigo-50 text-slate-800">
      {/* Navbar */}
      <header className="sticky top-0 z-40 backdrop-blur bg-white/70 border-b border-slate-200">
        <nav className="max-w-7xl mx-auto flex items-center justify-between px-4 sm:px-6 lg:px-8 h-16">
          <a href="#home" className="flex items-center gap-2 font-semibold text-slate-900">
            <span className="inline-flex h-8 w-8 items-center justify-center rounded-xl bg-indigo-600 text-white font-bold">A</span>
            <span>Ameya</span>
          </a>
          <div className="hidden md:flex items-center gap-6 text-sm">
            <a href="#features" className="hover:text-slate-900 text-slate-600">Features</a>
            <a href="#work" className="hover:text-slate-900 text-slate-600">Work</a>
            <a href="#pricing" className="hover:text-slate-900 text-slate-600">Pricing</a>
            <a href="#about" className="hover:text-slate-900 text-slate-600">About</a>
            <a href="#contact" className="hover:text-slate-900 text-slate-600">Contact</a>
          </div>
          <div className="flex items-center gap-3">
            <a href="#contact" className="hidden sm:inline-block"><Button className="rounded-2xl bg-indigo-600 hover:bg-indigo-700">Start a Project</Button></a>
          </div>
        </nav>
      </header>

      {/* Hero */}
      <Section id="home" className="pt-16">
        <div className="grid lg:grid-cols-2 gap-10 items-center py-16">
          <motion.div {...fadeUp}>
            <p className="inline-flex items-center gap-2 text-xs font-medium px-3 py-1 rounded-full bg-indigo-100 text-indigo-700 border border-indigo-200">
              <Sparkles className="h-4 w-4" /> BOUNDLESS • LIMITLESS
            </p>
            <h1 className="mt-4 text-4xl sm:text-5xl font-extrabold tracking-tight text-slate-900">
              Company Research & Lead Generation <span className="bg-gradient-to-r from-indigo-500 to-fuchsia-600 bg-clip-text text-transparent">that scales with you</span>
            </h1>
            <p className="mt-4 text-slate-600 text-lg max-w-xl">
              Ameya helps businesses grow with data-driven research, email campaigns, template creation, inbound management, and backend support. We make your operations smoother, faster, and limitless.
            </p>
            <div className="mt-6 flex flex-wrap items-center gap-3">
              <Button size="lg" className="rounded-2xl bg-indigo-600 hover:bg-indigo-700"><Rocket className="mr-2 h-4 w-4"/>Get a Free Consultation</Button>
              <a href="#work"><Button variant="outline" size="lg" className="rounded-2xl">See Our Work</Button></a>
            </div>
            <ul className="mt-6 grid sm:grid-cols-3 gap-3 text-sm text-slate-600">
              {["Company Research", "Lead Generation", "Email Campaigns"].map((item) => (
                <li key={item} className="flex items-center gap-2"><Check className="h-4 w-4 text-indigo-600"/>{item}</li>
              ))}
            </ul>
          </motion.div>
          <motion.div {...fadeUp} className="relative">
            <div className="aspect-[4/3] w-full rounded-3xl bg-gradient-to-tr from-indigo-600 to-fuchsia-600 p-1 shadow-xl">
              <div className="h-full w-full rounded-2xl bg-white grid place-items-center">
                <div className="p-6 text-center">
                  <Shield className="mx-auto h-10 w-10 text-slate-900"/>
                  <h3 className="mt-2 font-semibold">Reliable Growth Partner</h3>
                  <p className="mt-1 text-sm text-slate-600 max-w-sm">
                    From research to campaigns, we empower your business backend so you can focus on growth.
                  </p>
                </div>
              </div>
            </div>
          </motion.div>
        </div>
      </Section>

      {/* Features */}
      <Section id="features" className="py-16">
        <motion.div {...fadeUp} className="text-center max-w-3xl mx-auto">
          <h2 className="text-3xl sm:text-4xl font-bold text-slate-900">Our Core Services</h2>
          <p className="mt-2 text-slate-600">Ameya provides scalable solutions in research, outreach, and backend operations.</p>
        </motion.div>
        <div className="mt-10 grid sm:grid-cols-2 lg:grid-cols-3 gap-6">
          {[
            { icon: Rocket, title: "Lead Generation", desc: "Identify and engage high-quality prospects." },
            { icon: Shield, title: "Company Research", desc: "Data-driven insights for informed decisions." },
            { icon: Sparkles, title: "Email Campaigns", desc: "Craft and send impactful outreach." },
            { icon: Check, title: "Template Creation", desc: "Professional templates to streamline work." },
            { icon: Mail, title: "Inbound Management", desc: "Handle responses and workflows seamlessly." },
            { icon: Phone, title: "Backend Support", desc: "Dependable operational assistance." },
          ].map(({ icon: Icon, title, desc }) => (
            <Card key={title} className="rounded-2xl">
              <CardHeader>
                <div className="h-10 w-10 rounded-xl bg-indigo-600 text-white grid place-items-center">
                  <Icon className="h-5 w-5"/>
                </div>
                <CardTitle className="mt-3">{title}</CardTitle>
                <CardDescription>{desc}</CardDescription>
              </CardHeader>
            </Card>
          ))}
        </div>
      </Section>

      {/* Pricing */}
      <Section id="pricing" className="py-16">
        <motion.div {...fadeUp} className="text-center max-w-3xl mx-auto">
          <h2 className="text-3xl sm:text-4xl font-bold text-slate-900">Flexible Pricing</h2>
          <p className="mt-2 text-slate-600">Choose the plan that fits your growth stage.</p>
        </motion.div>
        <div className="mt-10 grid md:grid-cols-3 gap-6">
          {[{
            name: "Starter",
            price: "$499",
            blurb: "Research + 1 Email Campaign",
            features: ["Basic Research", "100 Leads", "1 Campaign", "Email Support"],
          },{
            name: "Growth",
            price: "$1,499",
            blurb: "Research + 3 Campaigns + Templates",
            features: ["Advanced Research", "500 Leads", "3 Campaigns", "Template Setup"],
          },{
            name: "Enterprise",
            price: "Custom",
            blurb: "End-to-end backend & inbound management",
            features: ["Unlimited Research", "Ongoing Campaigns", "Custom Templates", "Dedicated Support"],
          }].map((tier, idx) => (
            <Card key={tier.name} className={`rounded-2xl ${idx === 1 ? 'ring-2 ring-indigo-500' : ''}`}>
              <CardHeader>
                <CardTitle>{tier.name}</CardTitle>
                <CardDescription>{tier.blurb}</CardDescription>
              </CardHeader>
              <CardContent>
                <div className="text-4xl font-extrabold">{tier.price}{tier.price !== "Custom" && <span className="text-base font-medium text-slate-500"> USD</span>}</div>
                <ul className="mt-4 space-y-2 text-sm text-slate-700">
                  {tier.features.map((f) => (
                    <li key={f} className="flex items-center gap-2"><Check className="h-4 w-4 text-indigo-600"/>{f}</li>
                  ))}
                </ul>
                <div className="mt-6">
                  <Button className="w-full rounded-2xl bg-indigo-600 hover:bg-indigo-700">Choose {tier.name}</Button>
                </div>
              </CardContent>
            </Card>
          ))}
        </div>
      </Section>

      {/* About */}
      <Section id="about" className="py-16">
        <div className="grid lg:grid-cols-2 gap-10 items-center">
          <motion.div {...fadeUp}>
            <h2 className="text-3xl font-bold text-slate-900">About Ameya</h2>
            <p className="mt-3 text-slate-600">
              At Ameya, we believe in boundless possibilities. We specialize in backend solutions, from research and lead generation to inbound management, helping businesses scale without limits.
            </p>
            <div className="mt-4 grid sm:grid-cols-3 gap-4">
              {[{k:"Clients",v:"200+"},{k:"Projects",v:"500+"},{k:"Years",v:"10"}].map(({k,v}) => (
                <div key={k} className="rounded-2xl border border-slate-200 bg-white p-4">
                  <div className="text-2xl font-bold">{v}</div>
                  <div className="text-sm text-slate-600">{k}</div>
                </div>
              ))}
            </div>
          </motion.div>
          <motion.div {...fadeUp} className="rounded-3xl overflow-hidden border border-slate-200 bg-white">
            <div className="aspect-[16/10] grid place-items-center text-slate-500">
              <span className="text-sm">Replace with team photo / workflow diagram</span>
            </div>
          </motion.div>
        </div>
      </Section>

      {/* Contact */}
      <Section id="contact" className="py-16">
        <motion.div {...fadeUp} className="text-center max-w-2xl mx-auto">
          <h2 className="text-3xl sm:text-4xl font-bold text-slate-900">Get in Touch</h2>
          <p className="mt-2 text-slate-600">Share your requirements and we’ll respond within 24 hours.</p>
        </motion.div>
        <div className="mt-10 grid lg:grid-cols-3 gap-6">
          <Card className="lg:col-span-2 rounded-2xl">
            <CardContent className="p-6 space-y-4">
              <div className="grid sm:grid-cols-2 gap-4">
                <Input placeholder="Your name" />
                <Input placeholder="Email address" type="email" />
              </div>
              <Input placeholder="Company / Website" />
              <Textarea placeholder="Tell us about your goals…" rows={6} />
              <div className="flex items-center justify-between">
                <div className="text-xs text-slate-500">By submitting you agree to our privacy policy.</div>
                <Button className="rounded-2xl bg-indigo-600 hover:bg-indigo-700">Send Inquiry</Button>
              </div>
            </CardContent>
          </Card>
          <div className="space-y-4">
            <Card className="rounded-2xl">
              <CardHeader>
                <CardTitle>Contact</CardTitle>
                <CardDescription>Reach us directly</CardDescription>
              </CardHeader>
              <CardContent className="space-y-2 text-sm">
                <div className="flex items-center gap-2"><Mail className="h-4 w-4"/>hello@ameya.co</div>
                <div className="flex items-center gap-2"><Phone className="h-4 w-4"/>+91 98765 43210</div>
                <div className="flex items-center gap-2"><MapPin className="h-4 w-4"/>Bengaluru, IN</div>
              </CardContent>
            </Card>
            <Card className="rounded-2xl">
              <CardHeader>
                <CardTitle>FAQ</CardTitle>
                <CardDescription>Quick answers</CardDescription>
              </CardHeader>
              <CardContent className="text-sm text-slate-700 space-y-2">
                <p><span className="font-medium">How soon can you deliver?</span> Most projects are delivered within 1–3 weeks.</p>
                <p><span className="font-medium">Do you provide ongoing support?</span> Yes, we offer continuous backend and campaign management.</p>
              </CardContent>
            </Card>
          </div>
        </div>
      </Section>

      {/* Footer */}
      <footer className="mt-16 border-t border-slate-200">
        <Section className="py-10 flex flex-col sm:flex-row items-center justify-between gap-4">
          <div className="text-sm text-slate-600">© {new Date().getFullYear()} Ameya. All rights reserved.</div>
          <div className="flex items-center gap-4 text-sm">
            <a href="#features" className="text-slate-600 hover:text-slate-900">Features</a>
            <a href="#pricing" className="text-slate-600 hover:text-slate-900">Pricing</a>
            <a href="#about" className="text-slate-600 hover:text-slate-900">About</a>
            <a href="#contact" className="text-slate-600 hover:text-slate-900">Contact</a>
          </div>
        </Section>
      </footer>

      {/* Tiny QoL styles */}
      <style>{`
        html { scroll-behavior: smooth; }
      `}</style>
    </div>
  );
}
