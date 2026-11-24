# Tessellate patch set: AppliedEnergistics/Applied-Energistics-2
- Base: `ef54477d756dca07800904777b3b4b1f400f4bcb` (tag neoforge/v19.2.20)
- Patches (apply in order): `0001-tick-queues-and-be-repo.patch` `0002-grid-lifecycle-off-main-deferral.patch` `0003-statics-and-registries.patch` 
- Apply: `bash tessellate/apply.sh <checkout at base>` = `git apply --3way` each, fail hard
- Build: `bash ./gradlew jar -x test -Pversion=19.2.20 --no-daemon` (JDK 21); `tessellate/finalize.py` appends "Patched for Tessellate async region ticking." to description, jar -> `<name>-tessellate.jar`; modId/version untouched
- Maven: `com.wf.tessellate:appliedenergistics2-tessellate:<modVersion>-SNAPSHOT` @ https://repo.warfactory.co/snapshots, Gradle unique-snapshot layout (timestamped jar/pom + maven-metadata.xml + checksums) (secrets WARFACTORY_MAVEN_USER/TOKEN)
- CI: `.github/workflows/tessellate-patched.yml`
