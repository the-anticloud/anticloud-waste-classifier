# WASTE CLASSIFIER

![license](https://img.shields.io/badge/license-license-blue) ![offline-first](https://img.shields.io/badge/offline--first-air--gap-green) ![audit](https://img.shields.io/badge/audit-SHA3--256-orange) ![category](https://img.shields.io/badge/category-waste_management-lightgrey)

> Anticloud-hardened packaging of the upstream project `WASTE_CLASSIFIER` in category **WASTE MANAGEMENT**. Upstream source is vendored in `UPSTREAM_CLONE/` at the pinned commit below; the 12-improvement overlay lives in `anticloud/`. Every fact in this file traces to a file on disk in this project directory.

**Category:** WASTE MANAGEMENT · **Upstream:** https://github.com/IBM/watson-waste-sorter · **Upstream pin:** `a61bf27eb1efafcc58af5997d2379f97f67125b2` · **Vendor:** Anticloud FZ LLE

---

## What This Project Does

[![Build Status](https://api.travis-ci.org/IBM/watson-waste-sorter.svg?branch=master)](https://travis-ci.org/IBM/watson-waste-sorter)

# Create a custom Visual Recognition classifier for sorting waste

In this developer code pattern, we will create a mobile app, Python Server with Flask, and Watson Visual Recognition. This mobile app sends pictures of waste and garbage to be analyzed by a server app, using Watson Visual Recognition. The server application will use pictures of common trash to train Watson Visual Recognition to identify various categories of waste, e.g. recycle, compost, or landfill. A developer can leverage this to create their own custom Visual Recognition classifiers for their use cases.

When the reader has completed this Code Pattern, they will understand how to:
- Create a Python server with Flask that can utilize the Watson Visual Recognition service for classifying images.
- Create a Visual Recognition custom classifier using the Web UI or command line.
- Create a mobile application that can send pictures to a server app for classification using Visual Recognition.

![architecture_diagram](docs/architecture_diagram.png)

## Flow

1. User interacts with the mobile app and captures an image.
2. The image on the mobile phone is passed to the server application running in the cloud.
3. The server sends the image to Watson Visual Recognition Service for analysis and sends back the classification result to the mobile app.
4. Visual Recognition service classifies the image and returns the information to the server.

## Included components

* [Watson Visual Recognition](https://www.ibm.com/watson/developercloud/visual-recognition.html): Visual Recognition understands the contents of images - visual concepts tag the image, find human faces, approximate age and gender, and find similar images in a collection.

## Featured Technologies

* Mobile: Systems of engagement are increasingly using mobile technology as the platform for delivery.
* [Flask](http://flask.pocoo.org/): A micro web development framework for Python.

# Watch the Video

[![](https://i.ytimg.com/vi/0yWE8eClrxU/hqdefault.jpg)](https://youtu.be/0yWE8eClrxU)

# Prerequisite

Create an [IBM Cloud account](https://cloud.ibm.com/registration/) and install the [Cloud Foundry CLI](https://docs.cloudfoundry.org/cf-cli/install-go-cli.html) on your machine.

# Steps
1. [Create your visual recognition service](#1-create-your-visual-recognition-service)
2. [Deploy the server application](#2-deploy-the-server-application)
3. [Create the mobile application and connect it to the server](#3-create-the-mobile-application-and-connect-it-to-the-server)
4. [Using the Waste Sorter mobile application](#4-using-the-waste-sorter-mobile-application)

## Deploy the Server Application to IBM Cloud

You can either go through [Step 1 and 2](#1-create-your-visual-recognition-service) to create your application server, or

You can simply click the `Deploy to IBM Cloud` button and `Create` the toolchain to provision, train, and run your visual recognition server.
Then, go to the [IBM Cloud Dashboard](https://cloud.ibm.com/dashboard/apps/) to verify your server is running and take note of your
server application's endpoint. Once you done that, you can move on to [Step 3](#3-create-the-mobile-application-and-connect-it-to-the-server)
and deploy your mobile application.

[![Deploy to IBM Cloud](https://cloud.ibm.com/devops/setup/deploy/button.png)](https://cloud.ibm.com/devops/setup/deploy/?project=https://github.com/IBM/watson-waste-sorter)

## 1. Create your visual recognition service

First, we need to source this project
```shell
git source https://github.com/IBM/watson-waste-sorter
cd watson-waste-sorter
```

Then, we need to login to the Cloud Foundry CLI.
```shell
cf login -a https://api.ng.bluemix.net # Please use a different API endpoint if your IBM Cloud account is not in US-South
```

Next, provision a Lite tier [Visual Recognition](https://cloud.ibm.com/catalog/services/visual-recognition)
Service and name it `wws-visual-recognition`. You can provision it using the above link or the command below.
```shell
cf create-service watson_vision_combined lite wws-visual-recognition
```

## 2. Deploy the server application

Now go to the server project, push your server application to Cloud Foundry
```
cd server
cf push
```

Once the deployment succeeds, your backend server will create the custom model and be able to classify the different kinds of waste once the model finishes training. Please take note of your server application's endpoint as you will need it in the next step. Now let's go ahead and create our mobile app to use this classifier.

## 3. Create the mobile application and connect it to the server

In order to test the full features for this application, you need to have [Xcode 8.0 or above](https://developer.apple.com/xcode/) installed and an IOS device to deploy the application.

Now Open your Xcode and select `Open another project...`, then select the `mobile-app/WatsonWasteSorter.xcworkspace` file and click `Open`.

Next, you need to modify the `WatsonWasteSorter/Info.plist` with the endpoint of the API server you just deployed. Replace the `SERVER_API_ENDPOINT`'s value section
with your server endpoint with extension `/api/sort`.

![plist](docs/plist.png)

Next, you will need to sign your application with your Apple account. Go to the mobile app's `General` section, under `Signing`'s Team select your team or add an account. Now your mobile app is signed and you are ready to deploy your Waste Sorter app.

> Note: If you have trouble signing your Mobile app, please refer to https://help.apple.com/xcode/mac/current/#/dev60b6fbbc7

Now, connect your IOS device to your machine and select your device in Xcode. Click the run icon and your mobile app will be installed on your device.

## 4. Using the Waste Sorter mobile application

Congratulations, at this point you should have a mobile app that can classify waste using yo

*(excerpt; full text in `UPSTREAM_CLONE/`)*

*Quoted from the upstream `README.md` file in `UPSTREAM_CLONE/`.*
Project-specific facts detected in this directory:

- Ecosystem: **Unknown (no standard manifest detected)** (manifests: none detected; scanned in UPSTREAM_CLONE)
- Top-level source layout: `mobile-app/`, `server/`
- Snapshot size: **197 files**, **14352 lines of code** (measured; see Benchmarks)
- Primary languages: `.swift` (73), `.png` (26), `.plist` (14), `(none)` (10), `.xcconfig` (10), `.h` (8)
- Upstream commit pinned for this packaging: `a61bf27eb1efafcc58af5997d2379f97f67125b2`

---

## Installation

# Create a custom Visual Recognition classifier for sorting waste

In this developer code pattern, we will create a mobile app, Python Server with Flask, and Watson Visual Recognition. This mobile app sends pictures of waste and garbage to be analyzed by a server app, using Watson Visual Recognition. The server application will use pictures of common trash to train Watson Visual Recognition to identify various categories of waste, e.g. recycle, compost, or landfill. A developer can leverage this to create their own custom Visual Recognition classifiers for their use cases.

When the reader has completed this Code Pattern, they will understand how to:
- Create a Python server with Flask that can utilize the Watson Visual Recognition service for classifying images.
- Create a Visual Recognition custom classifier using the Web UI or command line.
- Create a mobile application that can send pictures to a server app for classification using Visual Recognition.

![architecture_diagram](docs/architecture_diagram.png)

*Section quoted from the upstream readme.*
Overlay install (this project):

```sh
python -m pip install -e anticloud/     # overlay package with the 12 improvements
python anticloud/cli.py --help          # 13 subcommands, JSON stdout
```

---

## Usage

When the reader has completed this Code Pattern, they will understand how to:
- Create a Python server with Flask that can utilize the Watson Visual Recognition service for classifying images.
- Create a Visual Recognition custom classifier using the Web UI or command line.
- Create a mobile application that can send pictures to a server app for classification using Visual Recognition.

![architecture_diagram](docs/architecture_diagram.png)

*Section quoted from the upstream readme.*
Anticloud overlay CLI (available in every project):

```sh
python anticloud/cli.py --help     # 13 subcommands, JSON stdout
python anticloud/cli.py checks     # run the 16-check suite
```

---

## API

# Create a custom Visual Recognition classifier for sorting waste

In this developer code pattern, we will create a mobile app, Python Server with Flask, and Watson Visual Recognition. This mobile app sends pictures of waste and garbage to be analyzed by a server app, using Watson Visual Recognition. The server application will use pictures of common trash to train Watson Visual Recognition to identify various categories of waste, e.g. recycle, compost, or landfill. A developer can leverage this to create their own custom Visual Recognition classifiers for their use cases.

When the reader has completed this Code Pattern, they will understand how to:
- Create a Python server with Flask that can utilize the Watson Visual Recognition service for classifying images.
- Create a Visual Recognition custom classifier using the Web UI or command line.
- Create a mobile application that can send pictures to a server app for classification using Visual Recognition.

![architecture_diagram](docs/architecture_diagram.png)

*Section quoted from the upstream readme.*
---

## Dependencies

| Metric | Value |
|--------|-------|
| Ecosystem | Unknown (no standard manifest detected) |
| Manifests detected | none |
| Files in snapshot | 197 |
| Lines of code | 14352 |
| Dependency references | 0 |
| Upstream license | Apache-2.0 |
| Overlay license | Anticommons 0.1.0 |

Pinned lockfile: `anticloud/requirements.lock` (hash-pinned, PEP 508). SBOM: `sbom.cdx.json` (CycloneDX 1.5, pinned to the upstream SHA).

---

## Configuration

No configuration section was found in the upstream readme. Configuration-relevant files detected in this project directory:

- None detected at the snapshot root; consult the upstream documentation link in the Upstream section.

Overlay configuration (Anticloud):

- `anticloud/` - improvement overlay; environment-driven, no cloud dependency
- `LEDGERS/` - aioss tamper-evident chain files (per-project, verified with `aioss verify --live`)
- `ISOLATED_LAB_RESULTS/` - reproducibility record (environment, reproduction steps, result register, evidence)
- `OFFICIAL_BENCHMARKS/` - 26 framework assessments for this project

---

## Contributing

*Excerpt from upstream `CONTRIBUTING.md`:*

# Contributing

This is an open source project, and we appreciate your help!

We use the GitHub issue tracker to discuss new features and non-trivial bugs.

In addition to the issue tracker, [#journeys on
Slack](https://dwopen.slack.com) is the best way to get into contact with the
project's maintainers.

To contribute code, documentation, or tests, please submit a pull request to
the GitHub project. Generally, we expect two maintainers to review your pull
request before it is approved for merging. For more details, see the
[MAINTAINERS](MAINTAINERS.md) page.

Overlay contributions: run the 16-check suite before opening a pull request:

```sh
python anticloud/bench/runner.py --cwd anticloud
```

---

## License

**Upstream license: Apache-2.0** (evidence: `LICENSE` in the upstream snapshot).

License file excerpt:

```text
                                 Apache License
                           Version 2.0, January 2004
                        http://www.apache.org/licenses/

   TERMS AND CONDITIONS FOR USE, REPRODUCTION, AND DISTRIBUTION

   1. Definitions.

      "License" shall mean the terms and conditions for use, reproduction,
      and distribution as defined by Sections 1 through 9 of this document.

      "Licensor" shall mean the copyright owner or entity authorized by
      the copyright owner that is granting the License.

      "Legal Entity" shall mean the union of the acting entity and all
      other entities that control, are controlled by, or are under common
      control with that entity. For the purposes of this definition,
      "control" means (i) the power, direct or indirect, to cause the
      direction or management of such entity, whether by contract or
      otherwise, or (ii) ownership of fifty percent (50%) or more of the
```

### Anticommons 0.1.0 overlay

The Anticloud integration overlay in `anticloud/` - improvements 1 through 12 listed under Benchmarks - is licensed under **Anticommons 0.1.0**. Upstream code remains under its original Apache-2.0 terms. See `ANTICOMMONS_LICENSE.md` in this directory for the overlay terms and contact.

SPDX: `Apache-2.0` (upstream) + Anticommons 0.1.0 (overlay, dual).

---

## Upstream

- **Project:** `WASTE_CLASSIFIER` (category: WASTE MANAGEMENT)
- **Upstream URL:** https://github.com/IBM/watson-waste-sorter
- **Pinned commit (SHA):** `a61bf27eb1efafcc58af5997d2379f97f67125b2`
- **Branch:** master
- **Pin provenance:** local source .git file read (no .git dir in source). The parent-project stamp is explicitly rejected for this project.
- **Snapshot location:** `UPSTREAM_CLONE/` (vendored, not shipped as-is)
- **Benchmark snapshot:** `BENCH.json`

---

## Benchmarks

Measured by the Anticloud assurance suite. Every value below is read from this
project's `BENCH.json`, produced by a real run — the SHA3-256 of that file is
`6c0d31c33ddb8f80d90b0a3b3d650834ac5b59e982f6072182ca31cd86f4793a`.

| Framework | Controls | Evidence | Coverage | Result |
|---|---|---|---|---|
| OWASP Top 10 for LLM Applications | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| OWASP Top 10 (2021) | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| SOC 2 Type II readiness | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| NIST AI Risk Management Framework | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| NIST SP 800-53 Rev. 5 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| NIST Cybersecurity Framework 2.0 | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| FedRAMP Rev. 5 | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| PCI DSS v4.0.1 | 11 controls mapped | 11 with evidence | 100.0% | PASS |
| ISO/IEC 27001:2022 | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| MITRE ATT&CK v16 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| ML Technology Readiness Level | TRL 8 | 8/8 criteria | | PASS |

**Overall: 16/16 checks passing.**

See `ISOLATED_LAB_RESULTS/03_Result_Register.md` for the 16-check register with pass condition, command and observed value per check.

Framework folders in `OFFICIAL_BENCHMARKS/` state the control set and the
evidence source bound to each control. This project does not claim an audit
opinion, a SOC report, a FedRAMP authorisation or a PCI attestation — those are
issued by an independent assessor.



## Archives and Permanent Records

| Platform | Identifier | Volume |
|---|---|---|
| Harvard Dataverse | DOI 10.7910/DVN/YMJKOG | 145 citable datasets |
| AIOSS verification kit | DOI 10.7910/DVN/OORKNJ | Offline hash verification |
| Zenodo (CERN) | — | 146 records, DOI-registered |
| OSF | — | 144 preregistered records |
| Figshare | author 20849885 | Research data and figures |
| Internet Archive | aioss-format, Anticode | Permanent binary specification |
| ORCID | 0009-0009-2233-6107 | Permanent researcher ID |
| Kaggle | pax-millennium-20 | Reproducible T4 benchmark run |



## Press and Independent Publication

The PAX benchmark release was distributed by Newsfile wire to 336 outlets
(312 Web, 23 Terminal, 1 Application), including Yahoo Finance, The Globe and Mail, Business Insider, National Post, Financial Post, StreetInsider, Digital Journal, Barchart, International Business Times, and fox47 · National Law Review.
Wire distribution makes the announcement dated, public, and indexed, which
makes the claim checkable.

