# pb-3124-github-checks
<!-- Github check testing -->
[//]: # Trying to workout a PR trigger()

[//]: # Trying to workout another PR trigger()

org = Organization.find_by!(slug: "yisheng-lee")

build = Organization::Context.for(org) do
    pipeline = org.projects.find_by!(slug: "pb-3124-github-checks")
    build = pipeline.builds.find_by!(number: 14)
end

pp build.attributes.slice("id", "uuid", "number", "state", "blocked_state",
"commit", "branch", "created_at", "started_at", "finished_at")
build