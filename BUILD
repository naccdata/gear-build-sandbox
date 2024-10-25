__defaults__({
  pex_binary: dict(environment="local"),
  docker_image: dict(build_platform=["linux/amd64"]),
})

local_environment(
  name="local_linux",
  compatible_platforms=["linux_x86_64"],
  fallback_environment="docker",
  docker_env_vars=["AWS_PROFILE=profile"]
)

local_environment(
  name="local_osx",
  compatible_platforms=["macos_arm64"],
)

docker_environment(
  name="docker",
  platform="linux_x86_64",
  image="python:3.11-bullseye",
  docker_env_vars=["AWS_PROFILE=profile"]
)

python_requirements(
    name="reqs",
    module_mapping={"flywheel-sdk": ["flywheel"]},
    overrides={
        "flywheel-sdk": {
            "dependencies": ["//:reqs#pandas"]
        },
    },
)