# Secrets Management

## Overview

Sensitive values should not be stored directly in source code or committed to the repository. The project uses GitHub Actions encrypted secrets to protect sensitive configuration values used by the CI/CD workflow.

## GitHub Actions Secrets

The repository uses the GitHub Actions secret:

`DEVSECOPS_TEST_SECRET`

The secret is accessed through the GitHub Actions secrets context:

`${{ secrets.DEVSECOPS_TEST_SECRET }}`

The actual secret value is not stored in the source code or workflow configuration.

## Security Benefits

Using encrypted repository secrets reduces the risk of accidentally exposing sensitive values through source-code files or workflow configuration.

Secrets should only be accessed when required by a workflow and should never be printed to workflow logs.

## Security Considerations

Repository secrets should be protected with appropriate repository permissions. Sensitive values should not be committed to Git, included in documentation, or displayed in screenshots.

The project also uses Gitleaks to identify potential exposed credentials, tokens and other sensitive values in the repository.

## Conclusion

GitHub Actions encrypted secrets provide a controlled mechanism for handling sensitive values during CI/CD execution while keeping those values outside the source code.
