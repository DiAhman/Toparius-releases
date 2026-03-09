# End User License Agreement (EULA)

**Plextura Suite**
**Effective Date: March 8, 2026**

This End User License Agreement ("Agreement") is a legal agreement between you
(either an individual or a single entity, "Licensee" or "you") and DiAhman
Contracting, LLC ("Licensor," "we," or "us") for the Plextura Suite software,
including all module server components, agent components, web interfaces,
associated documentation, updates, and patches (collectively, the "Software").

The Plextura Suite currently includes the following modules: Toparius (network
visibility), Pinaxus (directory services), and Akronil (endpoint management).
Additional modules may be added to the Suite over time.

**BY INSTALLING, COPYING, OR OTHERWISE USING THE SOFTWARE, YOU AGREE TO BE BOUND
BY THE TERMS OF THIS AGREEMENT. IF YOU DO NOT AGREE, DO NOT INSTALL OR USE THE
SOFTWARE.**

---

## 1. Definitions

**"Authorized Users"** means employees, contractors, or agents of Licensee who
are authorized to use the Software on Licensee's behalf.

**"Documentation"** means the user guides, installation instructions, and other
documentation provided with the Software.

**"Instance"** means a single running installation of any Plextura Suite module
server component.

**"License Key"** means the unique key or credential provided by Licensor to
activate the Software, if applicable.

**"Module"** means an individual product within the Plextura Suite (e.g.,
Toparius, Pinaxus, Akronil), each licensed separately under this Agreement.

**"Plextura Account"** means the user account created through the Plextura
portal for managing licenses, entitlements, and module instances.

**"Plextura Cloud"** means the cloud services operated by Licensor for license
activation, entitlement management, software updates, relay connectivity, and
related services.

**"Third-Party Components"** means open-source software libraries and components
incorporated into the Software, as identified in the THIRD-PARTY-LICENSES file.

---

## 2. License Grant

### 2.1 Grant

Subject to the terms of this Agreement and payment of applicable fees, Licensor
grants Licensee a limited, non-exclusive, non-transferable, non-sublicensable
license to:

a. Install and operate the Software on systems owned or controlled by Licensee;
b. Use the Software for Licensee's internal business purposes;
c. Make a reasonable number of backup copies of the Software for disaster
   recovery purposes;
d. Deploy agent components on networks managed by Licensee on behalf of its
   clients.

### 2.2 Managed Service Provider (MSP) Use

If Licensee is a managed service provider, Licensee may use the Software to
manage networks, directories, and endpoints belonging to Licensee's clients,
provided that:

a. Each client's data remains logically separated within the Software;
b. Licensee does not grant clients direct access to the Software beyond the
   built-in client portal functionality;
c. Licensee remains responsible for compliance with this Agreement;
d. The number of clients does not exceed the limits of Licensee's license tier.

### 2.3 Entitlements

Each Module is licensed separately. Licensee's entitlements (which Modules are
active, at what tier, and with what limits) are determined by the Plextura
Account associated with the Instance. Entitlements may include limits on
devices, sites, agents, clients, and other resources as defined by the
applicable license tier.

### 2.4 Trial Licenses

Licensor may offer time-limited trial licenses for evaluation purposes. Trial
licenses are limited to one per Module per Plextura Account and include
reduced resource limits as defined at the time of trial provisioning. Trial
licenses are not for production use.

---

## 3. Restrictions

Licensee shall not, and shall not permit any third party to:

a. **Copy or Distribute** — Reproduce, distribute, publish, or make available
   the Software or any portion thereof to any third party, except as expressly
   permitted herein;

b. **Modify** — Modify, adapt, translate, or create derivative works based on
   the Software;

c. **Reverse Engineer** — Reverse engineer, decompile, disassemble, or
   otherwise attempt to derive the source code, algorithms, or data structures
   of the Software, except to the extent expressly permitted by applicable law
   notwithstanding this limitation;

d. **Sublicense** — Sublicense, rent, lease, loan, or otherwise transfer the
   Software or any rights therein;

e. **Remove Notices** — Remove, alter, or obscure any copyright, trademark, or
   other proprietary notices on the Software;

f. **Competitive Use** — Use the Software to develop a product or service that
   competes with the Software;

g. **Circumvent** — Circumvent or disable any license key, access control,
   activation mechanism, or usage limitation in the Software;

h. **Benchmark** — Publish or disclose performance benchmarks or comparisons of
   the Software without prior written consent from Licensor;

i. **Illegal Use** — Use the Software in violation of any applicable local,
   state, national, or international law or regulation.

---

## 4. Intellectual Property

### 4.1 Ownership

The Software, including all copies, modifications, and derivative works, is and
shall remain the exclusive property of Licensor. This Agreement does not convey
any ownership interest in the Software to Licensee. All rights not expressly
granted herein are reserved by Licensor.

### 4.2 Feedback

If Licensee provides suggestions, ideas, or feedback regarding the Software
("Feedback"), Licensor shall have a royalty-free, worldwide, irrevocable,
perpetual license to use and incorporate such Feedback into the Software without
obligation to Licensee.

### 4.3 Trademarks

"Plextura," "Toparius," "Pinaxus," "Akronil," and their respective logos are
trademarks of DiAhman Contracting, LLC. This Agreement does not grant Licensee
any right to use Licensor's trademarks except as necessary to identify the
Software in normal use.

---

## 5. Third-Party Components

### 5.1 Open-Source Software

The Software incorporates third-party open-source components licensed under
MIT, BSD, ISC, Apache-2.0, and other permissive licenses. These components are
identified in the THIRD-PARTY-LICENSES file distributed with the Software.

### 5.2 Third-Party License Terms

Each Third-Party Component is subject to its own license terms. To the extent
any Third-Party Component license requires that it be distributed under terms
different from this Agreement, the terms of that third-party license shall
govern with respect to that component only. Nothing in this Agreement limits
your rights under, or grants you rights that supersede, the terms of any
applicable Third-Party Component license.

### 5.3 Apache-2.0 Notice

The Software includes Apache ECharts, Copyright 2017-2025 The Apache Software
Foundation. This product includes software developed at The Apache Software
Foundation (https://www.apache.org/). The full Apache License 2.0 text and
NOTICE file are included in the THIRD-PARTY-LICENSES file.

---

## 6. Plextura Cloud and Data

### 6.1 Cloud Connectivity

The Software connects to Plextura Cloud for license activation, entitlement
verification, periodic check-in, software updates, and relay connectivity. An
internet connection is required for initial activation and periodic license
verification.

### 6.2 Data Transmitted to Cloud

When connecting to Plextura Cloud, the Software transmits:

- Module name and version
- Instance identifier
- Machine fingerprint (a one-way hash; not reversible to hardware details)
- License and entitlement status
- Check-in timestamp

The Software does **not** transmit Licensee's business data (network topology,
device information, client records, monitoring metrics, or any other data
entered into or collected by the Software) to Plextura Cloud.

### 6.3 Telemetry

The Software may include an optional, anonymous telemetry feature. Telemetry
is **disabled by default** and collects only aggregated, non-identifying usage
statistics. Licensee may enable or disable telemetry at any time in the
Software's settings. See the Privacy Policy for details.

### 6.4 Licensee Data

All network topology data, device information, client records, monitoring
metrics, and other data entered into or collected by the Software ("Licensee
Data") remains the sole property of Licensee and resides on Licensee's
infrastructure. Licensor has no right to access Licensee Data unless explicitly
authorized by Licensee for support purposes.

### 6.5 Plextura Account

A Plextura Account is required to activate the Software and manage
entitlements. Account data (email, name, organization) is processed in
accordance with the Privacy Policy.

---

## 7. Support and Updates

### 7.1 Updates

Licensor may, at its sole discretion, release updates, patches, or new versions
of the Software. The Software checks for available updates via Plextura Cloud.
Updates may be subject to additional or different terms.

### 7.2 Support

Support is provided in accordance with the support plan associated with
Licensee's license tier, if applicable. Licensor is not obligated to provide
support under free or evaluation licenses.

---

## 8. Warranty Disclaimer

**THE SOFTWARE IS PROVIDED "AS IS" AND "AS AVAILABLE" WITHOUT WARRANTY OF ANY
KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, TITLE, AND NONINFRINGEMENT.**

**LICENSOR DOES NOT WARRANT THAT:**
- **THE SOFTWARE WILL MEET LICENSEE'S REQUIREMENTS;**
- **THE SOFTWARE WILL OPERATE WITHOUT INTERRUPTION OR ERROR;**
- **DEFECTS IN THE SOFTWARE WILL BE CORRECTED; OR**
- **THE SOFTWARE IS FREE OF VIRUSES OR OTHER HARMFUL COMPONENTS.**

**LICENSEE ASSUMES ALL RISK ASSOCIATED WITH THE USE OF THE SOFTWARE, INCLUDING
THE RISK OF NETWORK DISRUPTION, DATA LOSS, OR SECURITY VULNERABILITIES.**

---

## 9. Limitation of Liability

### 9.1 Exclusion of Damages

**IN NO EVENT SHALL LICENSOR, ITS OFFICERS, DIRECTORS, EMPLOYEES, OR AGENTS BE
LIABLE FOR ANY INDIRECT, INCIDENTAL, SPECIAL, CONSEQUENTIAL, EXEMPLARY, OR
PUNITIVE DAMAGES, INCLUDING BUT NOT LIMITED TO LOSS OF PROFITS, DATA, GOODWILL,
BUSINESS INTERRUPTION, OR PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES, ARISING
OUT OF OR IN CONNECTION WITH THIS AGREEMENT OR THE USE OF THE SOFTWARE, HOWEVER
CAUSED AND UNDER ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, TORT (INCLUDING
NEGLIGENCE), STRICT LIABILITY, OR OTHERWISE, EVEN IF LICENSOR HAS BEEN ADVISED
OF THE POSSIBILITY OF SUCH DAMAGES.**

### 9.2 Cap on Liability

**LICENSOR'S TOTAL AGGREGATE LIABILITY ARISING OUT OF OR RELATED TO THIS
AGREEMENT SHALL NOT EXCEED THE GREATER OF (A) THE AMOUNTS PAID BY LICENSEE FOR
THE SOFTWARE IN THE TWELVE (12) MONTHS PRECEDING THE EVENT GIVING RISE TO THE
CLAIM, OR (B) ONE HUNDRED DOLLARS ($100 USD).**

### 9.3 Essential Purpose

**THE LIMITATIONS IN THIS SECTION SHALL APPLY EVEN IF ANY LIMITED REMEDY FAILS
OF ITS ESSENTIAL PURPOSE.**

---

## 10. Indemnification

Licensee agrees to indemnify, defend, and hold harmless Licensor and its
officers, directors, employees, and agents from and against any claims,
liabilities, damages, losses, and expenses (including reasonable attorney's
fees) arising out of or related to:

a. Licensee's use of the Software in violation of this Agreement;
b. Licensee's violation of any applicable law or regulation;
c. Any third-party claim arising from Licensee's use of the Software.

---

## 11. Term and Termination

### 11.1 Term

This Agreement is effective from the date Licensee first installs or uses the
Software and continues until terminated.

### 11.2 Termination by Licensee

Licensee may terminate this Agreement at any time by uninstalling the Software
and destroying all copies in Licensee's possession.

### 11.3 Termination by Licensor

Licensor may terminate this Agreement immediately upon written notice if
Licensee breaches any term of this Agreement and fails to cure such breach
within thirty (30) days of receiving notice.

### 11.4 Effect of Termination

Upon termination:

a. All rights granted under this Agreement shall immediately cease;
b. Licensee must uninstall the Software and destroy all copies;
c. Sections 4, 5, 6, 8, 9, 10, and 12 shall survive termination;
d. Termination shall not affect any accrued rights or obligations.

---

## 12. General Provisions

### 12.1 Governing Law

This Agreement shall be governed by and construed in accordance with the laws
of the State of Texas, United States, without regard to its conflict of laws
provisions.

### 12.2 Dispute Resolution

Any dispute arising under this Agreement shall be resolved exclusively in the
state or federal courts located in the State of Texas, and both parties consent
to the personal jurisdiction of such courts.

### 12.3 Export Compliance

Licensee shall comply with all applicable export laws and regulations of the
United States and other jurisdictions. Licensee shall not export or re-export
the Software to any country, person, or entity prohibited by applicable law.

### 12.4 Severability

If any provision of this Agreement is held to be invalid or unenforceable, the
remaining provisions shall remain in full force and effect.

### 12.5 Waiver

The failure of either party to enforce any right or provision of this Agreement
shall not constitute a waiver of such right or provision.

### 12.6 Assignment

Licensee may not assign or transfer this Agreement or any rights hereunder
without the prior written consent of Licensor. Licensor may assign this
Agreement freely.

### 12.7 Entire Agreement

This Agreement, together with the LICENSE file, Privacy Policy, and any
applicable order form or purchase agreement, constitutes the entire agreement
between the parties regarding the Software and supersedes all prior or
contemporaneous agreements, understandings, and communications.

### 12.8 Amendments

Licensor reserves the right to modify this Agreement at any time. Material
changes will be communicated through the Software's release notes or
documentation. Continued use of the Software after such changes constitutes
acceptance of the modified terms.

### 12.9 Notices

All notices under this Agreement shall be in writing and sent to:

**DiAhman Contracting, LLC**
Email: contact@di-ahman.com

---

## 13. Acknowledgment

BY INSTALLING OR USING THE SOFTWARE, LICENSEE ACKNOWLEDGES THAT LICENSEE HAS
READ THIS AGREEMENT, UNDERSTANDS IT, AND AGREES TO BE BOUND BY ITS TERMS AND
CONDITIONS.

---

Copyright (c) 2024-2026 DiAhman Contracting, LLC. All rights reserved.
