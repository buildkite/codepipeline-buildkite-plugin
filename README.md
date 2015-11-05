# AWS CodePipeline Buildkite Plugin

A [Buildkite plugin](https://buildkite.com/plugins) to trigger [AWS CodePipeline](https://aws.amazon.com/codepipeline/) releases from within your Buildkite build pipelines.

## Dependencies

* The [aws cli](https://aws.amazon.com/cli/) tool (configured with the correct credentials)
* `zip`

## Example

The following pipeline will zip and upload the code to the given S3 location, and then start a release on the "QA Release" pipeline in your AWS CodePipeline:

```yml
steps:
  - name: ":codepipeline: QA Release"
    plugins:
      buildkite/codepipeline:
        s3-location: s3://qa-release-code-bucket/release.zip
        start: QA Release
```

## Options

### `start`

The name of the pipeline to start a release.

### `s3-location`

The S3 location to zip and upload the code to. This is the same location your AWS CodePipeline source step should expect to find the code.

## Roadmap

* Add the code

## License

MIT (see [LICENSE](LICENSE))
