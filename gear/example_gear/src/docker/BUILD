file(name="manifest", source="manifest.json")

docker_image(name="example-gear",
             source="Dockerfile",
             dependencies=[":manifest", "gear/example_gear/src/python/example_app:bin"],
             image_tags=["0.0.1", "latest"])
