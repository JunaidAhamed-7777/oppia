# Oppia issue #21308: state-domain coverage evidence

Tested commit: `45a3f667a484ef946cabdf6996d8931ed235af6c` (one commit on top of develop `e8a4db95614b8254f01c8a80904a4cc54c3815d7`).

The official runner reported 692 passing tests in a single fresh run, with zero errors and failures. This is file-level coverage, not full backend coverage. No changes were made to the coverage configuration or its exclusions. The runner permits unrelated modules outside this targeted run to be below 100%.

```sh
python -m scripts.run_backend_tests --skip_install --test_targets core.domain.state_domain_test,core.domain.exp_domain_test,core.domain.question_domain_test,core.domain.draft_upgrade_services_test,core.domain.exp_services_test,core.domain.question_services_test,core.domain.exp_fetchers_test --generate_coverage_report --ignore_coverage
coverage report --include='*/core/domain/state_domain.py' -m
```

```text
Name                          Stmts   Miss Branch BrPart  Cover   Missing
-------------------------------------------------------------------------
core/domain/state_domain.py    1252      0    638      0   100%
-------------------------------------------------------------------------
TOTAL                          1252      0    638      0   100%
```

[Coverage report image rendered from the same local report](state-domain-coverage.png).
