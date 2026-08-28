# CKA Study Kit

A complete, hands-on study kit for the **Certified Kubernetes Administrator (CKA)** exam (Kubernetes v1.35), built around a local practice cluster you run yourself with Ubuntu Multipass.

Three self-contained pages, no build step, no dependencies:

| Page | What it is |
|------|------------|
| [**Flight plan**](flight-plan.html) | Exam format, the five domains by weight, a 6-week study schedule, and step-by-step setup for a 3-node cluster on Multipass. |
| [**Lab series**](lab-series.html) | Nineteen hands-on labs across all five domains — objective, exact commands, and the exam rationale for each. |
| [**Exam-day kit**](exam-day-kit.html) | One-page reference: shell setup, failure fingerprints, high-frequency commands, and time management. |

## Live site

If you enable **GitHub Pages** (see below), the kit is served at:

```
https://cobalt3.github.io/<repo-name>/
```

## Enable GitHub Pages

1. Push this repo to GitHub (commands below).
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Set the branch to `main` and the folder to `/ (root)`, then **Save**.
5. Wait ~1 minute; your site goes live at the URL above.

The included `.nojekyll` file tells Pages to serve the HTML as-is.

## The lab cluster

Every lab runs on a 3-node `kubeadm` cluster (1 control-plane + 2 workers) built with
[Multipass](https://multipass.run). Full setup is in the flight plan. In short:

```bash
multipass launch 22.04 --name cp    --cpus 2 --memory 2G --disk 10G
multipass launch 22.04 --name node1 --cpus 2 --memory 2G --disk 10G
multipass launch 22.04 --name node2 --cpus 2 --memory 2G --disk 10G
```

The cluster is deliberately installed one minor version **behind** the exam (v1.34) so you
can practice the `kubeadm upgrade` task.

## Notes

- Kubernetes and its tooling move fast. Before exam day, reconfirm the current scope,
  allowed-docs list, and version numbers on the
  [official CKA page](https://training.linuxfoundation.org/certification/certified-kubernetes-administrator-cka/).
- Practice environments worth using: [killercoda.com](https://killercoda.com) (free) and
  killer.sh (two sessions bundled with exam registration).

## License

Released under the [MIT License](LICENSE) — fork it, adapt it, share it.
