load("@io_bazel_rules_docker//java:image.bzl", "war_image")
load("@k8s_deploy//:defaults.bzl", "k8s_deploy")

package(default_visibility = ["//visibility:public"])

licenses(["notice"])  # Apache 2.0

war_image(
  name = "server",
  srcs = ["Servlet.java"],
  deps = [
    "@maven//:javax_servlet_javax_servlet_api",
  ],
  base = "@java_base//image"
)

k8s_deploy(
  name = "staging",
  args = [
    "--v=2",
  ],
  images = {
    "hello-http-image:latest": ":server",
  },
  template = "//hellohttp:deployment.json",
)