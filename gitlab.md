# Gitlab & Gitlab-CI TIPS

**Q: How to skip triggering gitlab pipeline by maven release plugin**

Add to job config: 
  ~~~
    except:
        variables:
          - $CI_COMMIT_MESSAGE =~ /maven-release-plugin/
  ~~~
 [reference](https://docs.gitlab.com/ee/ci/yaml/#onlyvariablesexceptvariables)
