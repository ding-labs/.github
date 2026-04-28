<div align="center">

# Ding Labs

### **Alerting that ships with the workload.**

`one binary · runs with your job, not next to it · shaped for ephemeral compute`

[![Website](https://img.shields.io/badge/ding.ing-0a0a0a?style=for-the-badge&labelColor=0a0a0a&color=00ADD8)](https://ding.ing)
[![GitHub](https://img.shields.io/badge/ding--labs-0a0a0a?style=for-the-badge&logo=github&logoColor=white&labelColor=0a0a0a)](https://github.com/ding-labs)
[![License](https://img.shields.io/badge/MIT-0a0a0a?style=for-the-badge&labelColor=0a0a0a&color=00ADD8)](https://opensource.org/licenses/MIT)

</div>

---

## `// about`

Most observability is shaped for long-running fleets — pull metrics from steady-state services into a central database, alert on the database. That shape doesn't fit ephemeral compute: a 4-minute CI job, a 90-minute training run, a 30-second batch ETL, a 10-minute game match.

We build tools shaped for **ephemeral compute**. They drop into the workload, evaluate in-process, and exit when the job exits. No agents. No dashboards. No cloud account. Push-based, stateless, single binary.

> Don't store it. Stream it. DING it.

---

## `// featured`

### [`ding`](https://github.com/ding-labs/ding) &nbsp; ![Go](https://img.shields.io/badge/-Go-00ADD8?style=flat-square&logo=go&logoColor=white) ![Status](https://img.shields.io/badge/-stable-00C853?style=flat-square)

**A stream-based alerting daemon that wraps your command.** The job emits events, DING evaluates rules in-process, alerts fire during the run *and* a summary fires when the job exits. Both die together.

```yaml
# .github/workflows/ci.yml
- run: |
    curl -sf https://start.ding.ing | sh
    ding run --config alerts.yaml -- pytest tests/
```

Auto-detects GitHub Actions, GitLab CI, CircleCI, Jenkins, Buildkite, and MLflow — `run_id`, `branch`, `commit`, `workflow` attach to every alert with zero config.

| Metric | Result | vs. Prometheus |
|---|---|---|
| Alert latency p50 | **4ms** | ~62s |
| Cold start p50 | **9ms** | 185ms |
| Throughput | **116k req/s** | — |
| Binary size | **5MB static** | — |

[`docs →`](https://ding.ing) &nbsp; [`benchmarks →`](https://github.com/ding-labs/ding/blob/main/BENCHMARKS.md) &nbsp; [`source →`](https://github.com/ding-labs/ding)

### [`ding-action`](https://github.com/ding-labs/ding-action) &nbsp; ![GitHub Actions](https://img.shields.io/badge/-Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)

**DING for GitHub Actions in one `uses:` line.** Alerts surface as inline annotations in the live log and the PR check, with a markdown summary on the workflow run page.

---

## `// stack`

![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-1a1a1a?style=for-the-badge&logo=linux&logoColor=FCC624)
![YAML](https://img.shields.io/badge/YAML-CB171E?style=for-the-badge&logo=yaml&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=for-the-badge&logo=mlflow&logoColor=white)
![Homebrew](https://img.shields.io/badge/Homebrew-FBB040?style=for-the-badge&logo=homebrew&logoColor=black)

---

## `// principles`

```
> shaped for ephemeral compute   CI jobs, training runs, batch ETL, game matches
> runs with the workload         in-process, not next to it; both die together
> push beats pull                stream events at the speed of your job
> stateless                      nothing to provision, nothing to clean up
> config in your repo            alerting is a dev artifact, not an ops one
> small, sharp tools             5MB binary, 9ms cold start, microseconds-not-minutes
```

---

## `// contact`

<a href="https://ding.ing"><img src="https://img.shields.io/badge/web-ding.ing-00ADD8?style=flat-square&labelColor=0a0a0a" alt="ding.ing"></a>
<a href="https://github.com/ding-labs"><img src="https://img.shields.io/badge/github-ding--labs-181717?style=flat-square&logo=github&logoColor=white&labelColor=0a0a0a" alt="GitHub"></a>

---

<div align="center">
<sub><code>built in the open · MIT licensed · push-based by default</code></sub>
</div>
