# familie-action-yarn-cache

Ved endringer, husk å tagge med en ny versjon, eks
```
git tag -a -m "Description of this release" vX
git push --follow-tags
```

Tas i bruk med:
```
- uses: navikt/familie-action-yarn-cache/@v1
- name: Yarn install
  run: yarn --prefer-offline --frozen-lockfile
```

I `familie-ef-sak-frontend` sin build som kjører for PR's så caches ikke dependabot sine byggen
https://github.com/navikt/familie-ef-sak-frontend/blob/master/.github/workflows/build_dev.yaml 
```
- uses: navikt/familie-action-yarn-cache/@v1
  if: github.actor != 'dependabot[bot]'
- name: Yarn install
  run: yarn --prefer-offline --frozen-lockfile
```
