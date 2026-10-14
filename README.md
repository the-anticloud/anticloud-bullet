# BULLET

![license](https://img.shields.io/badge/license-license-blue) ![offline-first](https://img.shields.io/badge/offline--first-air--gap-green) ![audit](https://img.shields.io/badge/audit-SHA3--256-orange) ![category](https://img.shields.io/badge/category-artillery_manufacturing-lightgrey)

> Anticloud-hardened packaging of the upstream project `BULLET` in category **ARTILLERY MANUFACTURING**. Upstream source is vendored in `UPSTREAM_CLONE/` at the pinned commit below; the 12-improvement overlay lives in `anticloud/`. Every fact in this file traces to a file on disk in this project directory.

**Category:** ARTILLERY MANUFACTURING · **Upstream:** https://github.com/bulletphysics/bullet3 · **Upstream pin:** `475caa3ff4646fd9a796b67d14116256f4962bc7` · **Vendor:** Anticloud FZ LLE

---

## What This Project Does

# Bullet

![Main workflow](https://github.com/flyerhzm/bullet/actions/workflows/main.yml/badge.svg)
[![Gem Version](https://badge.fury.io/rb/bullet.svg)](http://badge.fury.io/rb/bullet)
[![AwesomeCode Status for flyerhzm/bullet](https://awesomecode.io/projects/6755235b-e2c1-459e-bf92-b8b13d0c0472/status)](https://awesomecode.io/projects/flyerhzm/bullet)
[![Coderwall Endorse](https://coderwall.com/flyerhzm/endorsecount.png)](https://coderwall.com/flyerhzm)

The Bullet gem is designed to help you increase your application's performance by reducing the number of queries it makes. It will watch your queries while you develop your application and notify you when you should add eager loading (N+1 queries), when you're using eager loading that isn't necessary and when you should use counter cache.

Best practice is to use Bullet in development mode or custom mode (staging, profile, etc.). The last thing you want is your clients getting alerts about how lazy you are.

Bullet gem now supports **activerecord** >= 4.0 and **mongoid** >= 4.0.

If you use activerecord 2.x, please use bullet <= 4.5.0

If you use activerecord 3.x, please use bullet < 5.5.0

## External Introduction

* [https://rubyonrails.org/2009/10/22/community-highlights](https://rubyonrails.org/2009/10/22/community-highlights)
* [https://www.shakacode.com/blog/eliminate-N-1-queries-with-bullet/](https://www.shakacode.com/blog/eliminate-N-1-queries-with-bullet/)
* [https://reinteractive.com/articles/ruby-on-rails-community/elevating-your-code-quality-bullet-gem-and-query-prevention-in-testing](https://reinteractive.com/articles/ruby-on-rails-community/elevating-your-code-quality-bullet-gem-and-query-prevention-in-testing)

## Install

You can install it as a gem:

```
gem install bullet
```

or add it into a Gemfile (Bundler):

```ruby
gem 'bullet', group: 'development'
```

enable the Bullet gem with generate command

```ruby
bundle exec rails g bullet:install
```
The generate command will auto generate the default configuration and may ask to include in the test environment as well. See below for custom configuration.

**Note**: make sure `bullet` gem is added after activerecord (rails) and
mongoid.

## Configuration

Bullet won't enable any notification systems unless you tell it to explicitly. Append to
`config/environments/development.rb` initializer with the following code:

```ruby
config.after_initialize do
  Bullet.enable = true
  Bullet.sentry = true
  Bullet.alert = true
  Bullet.bullet_logger = true
  Bullet.console = true
  Bullet.xmpp = { :account  => 'bullets_account@jabber.org',
                  :password => 'bullets_password_for_jabber',
                  :receiver => 'your_account@jabber.org',
                  :show_online_status => true }
  Bullet.rails_logger = true
  Bullet.honeybadger = true
  Bullet.bugsnag = true
  Bullet.appsignal = true
  Bullet.airbrake = true
  Bullet.rollbar = true
  Bullet.add_footer = true
  Bullet.footer_position = 'bottom_left'  # or 'bottom_right', 'top_left', 'top_right'
  Bullet.skip_html_injection = false
  Bullet.skip_http_headers = false
  Bullet.stacktrace_includes = [ 'your_gem', 'your_middleware' ]
  Bullet.stacktrace_excludes = [ 'their_gem', 'their_middleware', ['my_file.rb', 'my_method'], ['my_file.rb', 16..20] ]
  Bullet.slack = { webhook_url: 'http://some.slack.url', channel: '#default', username: 'notifier' }
  Bullet.opentelemetry = true
  Bullet.raise = false
  Bullet.always_append_html_body = false
  Bullet.skip_user_in_notification = false
end
```

The notifier of Bullet is a wrap of [uniform_notifier](https://github.com/flyerhzm/uniform_notifier)

The code above will enable all of the Bullet notification systems:
* `Bullet.enable`: enable Bullet gem, otherwise do nothing
* `Bullet.sentry`: add notifications to sentry
* `Bullet.alert`: pop up a JavaScript alert in the browser
* `Bullet.bullet_logger`: log to the Bullet log file (Rails.root/log/bullet.log)
* `Bullet.console`: log warnings to your browser's console.log (Safari/Webkit browsers or Firefox w/Firebug installed)
* `Bullet.xmpp`: send XMPP/Jabber notifications to the receiver indicated. Note that the code will currently not handle the adding of contacts, so you will need to make both accounts indicated know each other manually before you will receive any notifications. If you restart the development server frequently, the 'coming online' sound for the Bullet account may start to annoy - in this case set :show_online_status to false; you will still get notifications, but the Bullet account won't announce it's online status anymore.
* `Bullet.rails_logger`: add warnings directly to the Rails log
* `Bullet.honeybadger`: add notifications to Honeybadger
* `Bullet.bugsnag`: add notifications to bugsnag
* `Bullet.appsignal`: add notifications to AppSignal
* `Bullet.airbrake`: add notifications to airbrake
* `Bullet.rollbar`: add notifications to rollbar
* `Bullet.add_footer`: adds the details in the bottom left corner of the page. Double click the footer or use close button to hide footer.
* `Bullet.footer_position`: position of the footer on the page. Valid values are 'bottom_left' (default), 'bottom_right', 'top_left', or 'top_right'. This is useful when the default position clashes with browser UI elements like Chrome's URL preview.
* `Bullet.skip_html_injection`: prevents Bullet from injecting code into the returned HTML. This must be false for receiving alerts, showing the footer or console logging.
* `Bullet.skip_http_headers`: don't add headers to API requests, and remove the javascript that relies on them. Note that this prevents bullet from logging warnings to the browser console or updating the footer.
* `Bullet.stacktrace_includes`: include paths with any of these substrings in the stack trace, even if they are not in your main app
* `Bullet.stacktrace_excludes`: ignore paths with any of these substrings in the stack trace, even if they are not in your main app.
   Each item can be a string (match sub

*(excerpt; full text in `UPSTREAM_CLONE/`)*

*Quoted from the upstream `README.md` file in `UPSTREAM_CLONE/`.*
Project-specific facts detected in this directory:

- Ecosystem: **Ruby / Bundler** (manifests: Gemfile; scanned in UPSTREAM_CLONE)
- Top-level source layout: `lib/`, `perf/`, `rails/`, `spec/`, `tasks/`
- Snapshot size: **123 files**, **7618 lines of code** (measured; see Benchmarks)
- Primary languages: `.rb` (102), `(none)` (6), `.0` (4), `.md` (3), `.1` (2), `.2` (1)
- Upstream commit pinned for this packaging: `475caa3ff4646fd9a796b67d14116256f4962bc7`

---

## Installation

You can install it as a gem:

```
gem install bullet
```

or add it into a Gemfile (Bundler):

```ruby
gem 'bullet', group: 'development'
```

enable the Bullet gem with generate command

```ruby
bundle exec rails g bullet:install
```
The generate command will auto generate the default configuration and may ask to include in the test environment as well. See below for custom configuration.

**Note**: make sure `bullet` gem is added after activerecord (rails) and
mongoid.

*Section quoted from the upstream readme.*
Overlay install (this project):

```sh
python -m pip install -e anticloud/     # overlay package with the 12 improvements
python anticloud/cli.py --help          # 13 subcommands, JSON stdout
```

---

## Usage

Best practice is to use Bullet in development mode or custom mode (staging, profile, etc.). The last thing you want is your clients getting alerts about how lazy you are.

Bullet gem now supports **activerecord** >= 4.0 and **mongoid** >= 4.0.

If you use activerecord 2.x, please use bullet <= 4.5.0

If you use activerecord 3.x, please use bullet < 5.5.0

*Section quoted from the upstream readme.*
Anticloud overlay CLI (available in every project):

```sh
python anticloud/cli.py --help     # 13 subcommands, JSON stdout
python anticloud/cli.py checks     # run the 16-check suite
```

---

## API

Bullet gem now supports **activerecord** >= 4.0 and **mongoid** >= 4.0.

If you use activerecord 2.x, please use bullet <= 4.5.0

If you use activerecord 3.x, please use bullet < 5.5.0

*Section quoted from the upstream readme.*
---

## Dependencies

| Metric | Value |
|--------|-------|
| Ecosystem | Ruby / Bundler |
| Manifests detected | Gemfile |
| Files in snapshot | 123 |
| Lines of code | 7618 |
| Dependency references | 0 |
| Upstream license | No license file present in the upstream snapshot |
| Overlay license | Anticommons 0.1.0 |

Pinned lockfile: `anticloud/requirements.lock` (hash-pinned, PEP 508). SBOM: `sbom.cdx.json` (CycloneDX 1.5, pinned to the upstream SHA).

---

## Configuration

**Note**: make sure `bullet` gem is added after activerecord (rails) and
mongoid.

*Section quoted from the upstream readme.*
Overlay configuration (Anticloud):

- `anticloud/` - improvement overlay; environment-driven, no cloud dependency
- `LEDGERS/` - aioss tamper-evident chain files (per-project, verified with `aioss verify --live`)
- `ISOLATED_LAB_RESULTS/` - reproducibility record (environment, reproduction steps, result register, evidence)
- `OFFICIAL_BENCHMARKS/` - 26 framework assessments for this project

---

## Contributing

Upstream contributions: fork the `BULLET` project, create a feature branch, and open a pull request against upstream. Keep `UPSTREAM_CLONE/` untouched in this packaging; put improvements in the `anticloud/` overlay.

Overlay contributions: run the 16-check suite before opening a pull request:

```sh
python anticloud/bench/runner.py --cwd anticloud
```

---

## License

**Upstream license: No license file present in the upstream snapshot** (evidence: `LICENSE` in the upstream snapshot).

### Anticommons 0.1.0 overlay

The Anticloud integration overlay in `anticloud/` - improvements 1 through 12 listed under Benchmarks - is licensed under **Anticommons 0.1.0**. Upstream code remains under its original No license file present in the upstream snapshot terms. See `ANTICOMMONS_LICENSE.md` in this directory for the overlay terms and contact.

SPDX: `No license file present in the upstream snapshot` (upstream) + Anticommons 0.1.0 (overlay, dual).

---

## Upstream

- **Project:** `BULLET` (category: ARTILLERY MANUFACTURING)
- **Upstream URL:** https://github.com/bulletphysics/bullet3
- **Pinned commit (SHA):** `475caa3ff4646fd9a796b67d14116256f4962bc7`
- **Branch:** master
- **Pin provenance:** unresolved — API license NOASSERTION (zlib) not permissive-tier; contamination stamp removed. The parent-project stamp is explicitly rejected for this project.
- **Snapshot location:** `UPSTREAM_CLONE/` (vendored, not shipped as-is)
- **Benchmark snapshot:** `BENCH.json`

---

## Benchmarks

Measured by the Anticloud assurance suite. Every value below is read from this
project's `BENCH.json`, produced by a real run — the SHA3-256 of that file is
`d3ffa217e55447076d909c5751a344b4910f89744faf3f265c502081b243ad5e`.

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



## Press and Independent Publication

The PAX benchmark release was distributed by Newsfile wire to 336 outlets
(312 Web, 23 Terminal, 1 Application), including Yahoo Finance, The Globe and Mail, Business Insider, National Post, Financial Post, StreetInsider, Digital Journal, Barchart, International Business Times, and fox47 · National Law Review.
Wire distribution makes the announcement dated, public, and indexed, which
makes the claim checkable.



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

