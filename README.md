# DevOps
шпаркалка по Git / Jenkins / GitLab / 

**Git**  
задать базовую информацию  
git config --global user.name "Алексей Якурнов"  
git config --global user.email "mail@mail.com"

**GitLab**  
создать runner

```
gitlab-runner register \  
  --non-interactive \  
  --url "https://gitlab.com/" \  
  --registration-token "PROJECT_REGISTRATION_TOKEN" \  
  --executor "docker" \  
  --docker-image alpine:latest \  
  --description "docker-runner" \  
  --maintenance-note "Free-form maintainer notes about this runner" \  
  --tag-list "docker,aws" \  
  --run-untagged="true" \  
  --locked="false" \  
  --access-level="not_protected"
```
