# sonar-scanner
Build a docker container for a given version of the Sonar Scanner

## Update workflow
To update the sonar scanner version, edit the Dockerfile's `SONAR_VERSION`
argument. Make sure you test afterwards since the URL that Sonar is fetched
from may not be stable.

Once the builds work, make your commit and `git push`.

Autobuilds are configured. This will update the `latest` tag. In order to
provide versioned tags, create a new tag with `git tag x.y.z.w`; by convention
this should match the `SONAR_VERSION` in the Dockerfile.

Finally, `git push origin x.y.z.w`. Autobuilds will create an image with
the tag `x.y.z.w`.