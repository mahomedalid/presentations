---
marp: true
theme: badgefed-theme
class: lead
paginate: true
backgroundColor: #1a1a2e
header: '**BadgeFed** - Decentralised Digital Badges'
footer: 'FOSDEM 2025 | badgefed.org'
---

<!-- _header: "" -->
<!-- _footer: "" -->

![bg left:20% 80%](https://badgefed.vocalcat.com/images/avatar.png)

# **Decentralised Badges with ActivityPub + OpenBadges**

## Building the Interoperable Credentialing System We Deserved

**FOSDEM 2025**  

---

<!-- _class: lead -->

![bg center:60% 70%](imgs/meme1.jpg)

---

<!-- _class: lead -->

![bg center: 75%](imgs/kiddo_with_somostech.png)

---

<!-- _class: lead -->

![bg center: 40%](imgs/dodgewhat.jpg)

---

<!-- _class: lead -->

![bg center: 40%](imgs/lawsuit.jpg)

---

<!-- _class: lead -->

![bg center: 40%](imgs/lawsuit.jpg)

---

<!-- _class: lead -->

![bg center: 40%](imgs/budgetplanning.jpg)

---

<!-- transition: fade -->

**CTO focus:**
- 🌐 Maintaining websites and systems
- 🎯 Content creation for hackathons  
- 🔧 Building community tools (interview simulators, mentorship platforms)
- 🤝 Organizing meetups and conferences with tech industry insiders

-.-

---


**CTO focus:**
- 🌐 Maintaining websites and systems
- 🎯 Content creation for hackathons  
- 🔧 Building community tools (interview simulators, mentorship platforms)
- 🤝 Organizing meetups and conferences with tech industry insiders

**Soon we realized:** All these activities needed **digital recognition**

---

<!-- _transition: none -->


---

# BadgeFed: Modern Features Demo\n\n<!-- _class: lead -->\n<!-- _backgroundColor: #1a1a2e -->\n\n## Code Example\n\n```csharp\n// ActivityPub Badge Creation\npublic async Task<Badge> CreateBadgeAsync(string badgeClassId)\n{\n    var badge = new OpenBadge {\n        Type = \"Achievement\",\n        BadgeClass = badgeClassId,\n        Recipient = recipient.Email\n    };\n    \n    return await _badgeService.IssueAsync(badge);\n}\n```\n\n> **Pro Tip:** *Combining ActivityPub + OpenBadges = Federation Magic* ✨\n\n---\n\n# The Need: Everyone Deserves Recognition

<!-- _backgroundColor: #0f3460 -->

**Who needed badges?**
- 🎤 **Speakers** at our events deserved acknowledgment
- 🙋 **Volunteers** needed recognition for contributions  
- 💻 **Hackathon participants** required skill verification
- 👥 **Mentors and mentees** earned credentials after tenure completion

---

**The Research:** *Credly by Pearson was the market leader*

**The Reality:** Proprietary platform with **vendor lock-in and no federation** 🔒

> *"Communities deserve interoperable, self-hosted solutions"*

---

# The Backburner: When Good Ideas Wait

![bg center 80%](good-idea-waiting.png)

<!-- Alt text for image generation: A lightbulb with a badge/credential icon inside it, sitting on a shelf labeled 'back burner' collecting dust, with a long priority list on a clipboard in the foreground showing 20-30 items, clock showing limited time, conveying frustration of having a solution but no resources to implement, warm lighting with a sense of waiting -->

---

# The Discovery: My ActivityPub Journey

![bg center 85%](activitypub-discovery-moment.png)

<!-- Alt text for image generation: A person at their computer with an expression of sudden realization and excitement, screen showing a blog connecting to a network of federated nodes, Twitter bird transforming into Mastodon elephant, network visualization with interconnected servers and data flowing between them, moment of discovery with bright enlightening colors, tech enthusiasm and breakthrough feeling -->

---

# The Decision: BadgeFed is Born

Armed with knowledge and a clear project vision—**something that wasn't just another social network clone**—I decided to create **BadgeFed**.

**Due Diligence Check:**
- 🔍 Found **ActivityBadges** (existing solution)
- 🛠️ Attempted setup and thorough exploration
- ❌ **Not ready** for SOMOS.tech's technology stack

**Solution:** Combine two powerful technologies: **ActivityPub + OpenBadges**

---

# Confession Time: The .NET Choice

![bg center 75%](dotnet-love-confession.png)

<!-- Alt text for image generation: A person sheepishly holding up a .NET logo with hearts floating around it, while standing in front of a crowd of penguin mascots (Linux) and other open source logos looking skeptical but amused, conveying vulnerability and humor about loving .NET in the fediverse community, light-hearted and endearing confession moment -->

---

# How BadgeFed Works: Technical Deep Dive

```json
{
  "@context": "https://www.w3.org/ns/activitystreams",
  "id": "https://badges.somos.tech/grant/123",
  "type": "Note",
  "content": "🏅 SOMOS.tech Community Leader Badge awarded to @maria",
  "attributedTo": "https://badges.somos.tech/actors/somos.tech",
  "attachment": [{
    "@context": "https://w3id.org/openbadges/v2",
    "type": "Assertion",
    "recipient": { "type": "url", "identity": "https://mastodon.social/@maria" },
    "badge": "https://badges.somos.tech/badges/community-leader",
    "verification": { "type": "HostedBadge" },
    "issuedOn": "2025-02-01T10:00:00Z"
  }]
}
```

---

# The Magic: Social Credentials

**Simple approach unlocks tremendous possibilities:**

- 👥 **Issuers can be followed** (ActivityPub verb)
- 💬 **Badges can be commented on** (replies)
- 🔄 **Shared, reposted, boosted** (social dynamics)
- 💭 **Even quoted** (social proof)

**We've added all the social dynamics to credentials!**

*When an issuer posts a badge, other issuers receive those notes, and voilà! Decentralized badges.*

---

# Federation Power: Relays & Networks

**Specialized actors that exclusively boost badges:**

- 🏛️ **University relays** - Educational institutions within countries
- 🎮 **Gaming relays** - Indie game achievements and accomplishments  
- 🏭 **Industry relays** - Professional certifications for specific sectors
- 🏛️ **Government relays** - Regional credential verification
- 🛠️ **Trade networks** - Specialized skills for arts and technical fields

**Result:** Instances can receive, verify, and distribute badges virtually anywhere

---

# Security & Trust: Triple Verification

## **Comprehensive Security Model**

1. **ActivityPub Signatures** - HTTP signatures verify sender authenticity
2. **OpenBadge Signatures** - Cryptographic integrity of badge data  
3. **Actor-Issuer Linking** - Badge issuer URL must match ActivityPub actor

## **Recipient Protection**
- Recipients must be mentioned in ActivityPub Note
- Prevents badge spoofing and misattribution
- Federated identity verification across platforms

---

# Real Impact: Not a Proof of Concept

![bg center 90%](real-impact-production.png)

<!-- Alt text for image generation: Split screen showing expensive Credly interface with $3000 price tag on left, versus happy diverse community members sharing badges on social media feeds on right, with counter showing 150+ and 89+ badges, people celebrating achievements, badges flowing through federated network, real community impact with authentic joy and social sharing, production-ready system in action -->

---

# The Wallet Revolution: Own Your Credentials

**Decentralized credential storage:**
- 📱 **Smartphone app** or self-hosted system
- 🏠 **Your domain, your control**
- 💾 **Persistent copies** even if issuers disappear
- 🔍 **Single verification point** for employers

**Unlike Mozilla Backpack:** Fully decentralized within the fediverse

**The Game Changer:** Any Mastodon user can issue badges using existing APIs

---

# Live Demo: See Federation in Action

## **Real-Time Badge Issuance Flow**

**Let's demonstrate:**
1. 🏅 **Create badge class** - "FOSDEM 2025 Attendee" 
2. 🎯 **Issue to recipient** - Mention @username
3. 🌐 **ActivityPub distribution** - Federated automatically
4. ✅ **Verification** - Check on recipient's timeline
5. 👀 **Cross-instance visibility** - Badge appears everywhere

*Watch how a badge travels from issuer to recipient across the fediverse in real-time!*

---

# Deploy in Minutes: Getting Started

## **Docker (Recommended)**
```bash
docker run -d -p 5000:80 \
  -e "MastodonConfig__Server=hachyderm.io" \
  -e "AdminAuthentication__AdminUsers__0__Id=admin" \
  -v $(pwd)/data:/app/data \
  badgefed/badgefed
```

## **5-Step Setup:**
1. Choose deployment (self-host or Community Credentials)
2. Configure OAuth (Mastodon/LinkedIn) 
3. Set up admin users
4. Create badge classes
5. **Start issuing!** - Awards federate automatically

---

# How YOU Can Build This Future

## **🛠️ As a Developer**
- **Core Development:** `github.com/tryvocalcat/badgefed`
- **UI/UX:** Build themes and improve user experience  
- **Integrations:** Connect with existing platforms and tools
- **Documentation:** Help others understand and implement
- **API Extensions:** Build new federation capabilities

## **🏛️ As an Organization**
- **Deploy:** Use BadgeFed for your community
- **Join Network:** Connect with Community Credentials
- **Share Stories:** Document your use cases and impact
- **Request Features:** Help shape development priorities

---

# Community & Resources

## **Get Started Today**
- 🚀 **GitHub:** `github.com/tryvocalcat/badgefed`
- 🏛️ **Hosted Support:** `communitycredentials.org`
- 💬 **Community:** Matrix/Discord channels for developers
- 📖 **Documentation:** Complete setup guides and API references

## **Join the Movement**
- **Blog:** `badgefed.vocalcat.com` - Latest updates and insights
- **SOMOS.tech:** `somos.tech` - Supporting Latino tech communities
- **Demo Instance:** Try it live at `demo.communitycredentials.org`

---

# Current Challenges: Help Us Solve These

## **Technical Challenges**
- 🔍 **Federation scaling** - Discovery across large networks
- 🔎 **Search & discovery** - Cross-instance badge search
- 🆔 **Identity portability** - Moving credentials between platforms
- 🛡️ **Moderation & trust** - Preventing spam and building reputation

## **Community Needs**
- 📚 **More documentation** and tutorials
- 🎨 **Better themes** and user interfaces
- 🔌 **Platform integrations** (GitHub, GitLab, Discord)
- 🌐 **Translation** for global communities

**Your expertise can make a difference!**

---

# The Vision: Social Credentialing Ecosystem

![bg center 95%](social-credentialing-future.png)

<!-- Alt text for image generation: A vibrant interconnected network of diverse people sharing and celebrating achievements, badges flowing freely between communities, teachers and students, conference speakers, volunteers being recognized, small businesses and customers, all connected in a decentralized web with no corporate walls or silos, achievements integrated into social feeds and daily digital life, warm community colors, empowering and inclusive future vision -->

---

# Use Cases: Beyond Nonprofits

## **Educational Institutions**
- 🎓 Student achievement tracking and portfolio building
- 📜 Continuing education credits and professional development
- 🔬 Research participation and academic contributions

## **Professional Communities** 
- 🎤 Conference attendance and speaker recognition
- 🏆 Skill certifications and competency validation
- 🤝 Community contributions and volunteer hours

## **Corporate & Training**
- 👔 Employee development and career progression
- ✅ Compliance tracking and mandatory training
- 🏅 Internal recognition and achievement systems

---

# Future Roadmap: What's Next

## **Short Term (2025)**
- 🔍 **Enhanced search** across federation networks
- 🏷️ **Badge collections** and digital portfolios
- 🔗 **Improved identity linking** and verification systems

## **Medium Term**
- 🤖 **AI-powered badge recommendations** and automation
- 📊 **Advanced analytics** for organizations and issuers
- 🌉 **Bridge integrations** with existing credential platforms

## **Long Term** 
- 🆔 **Decentralized identity** (DID) integration
- ⛓️ **Blockchain anchoring** for immutable records
- 🏛️ **Governance frameworks** for federation networks

---

# The Call to Action

**This is the future of recognition:** 
- 🌐 **Decentralized** - No single point of failure
- 🤝 **Social** - Integrated with how we communicate  
- 👥 **Community-owned** - Controlled by those who matter most

**The question isn't whether this will transform how we think about credentials and achievements—it's whether you'll help build this future with us.**

**Start today:**
- Fork the repo and contribute code
- Deploy an instance for your community  
- Join our developer community
- Share your ideas and use cases

---

![bg left:40% 80%](https://raw.githubusercontent.com/activitypub/activitypub/master/activitypub-logo.png)

# Thank You!

## **Let's Build the Future of Credentials Together**

🌐 **github.com/tryvocalcat/badgefed**  
🏛️ **communitycredentials.org**  
🤝 **somos.tech**  
💬 **Join our community channels**

*Questions? Let's federate some credentials and start the revolution!*

---

# Appendix: Quick Start Guide

## **One-Command Deploy**
```bash
# Docker deployment
docker run -d -p 5000:80 badgefed/badgefed

# Visit localhost:5000 and follow setup wizard
```

## **Essential Links**
- **Source Code:** `github.com/tryvocalcat/badgefed`
- **Documentation:** `/docs` folder in repository
- **ActivityPub Spec:** `w3.org/TR/activitypub`
- **Open Badges:** `openbadges.org`
- **Live Demo:** `demo.communitycredentials.org`

## **Community Support**
- **Matrix:** `#badgefed:matrix.org`
- **Discord:** Link in GitHub README
- **Issues & Feature Requests:** GitHub Issues