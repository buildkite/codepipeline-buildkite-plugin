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
      - buildkite/codepipeline:
          start: QA Release
          upload-to-s3: s3://qa-release-code-bucket/code.zip
```

## Options

### `start`

The name of the pipeline to start a release.

### `upload-to-s3` (optional)

The S3 location to zip and upload the code to before starting the CodePipeline release. This should be the same location your CodePipeline S3 "Source" step is configured with.

## Roadmap

* Add the code

## License

MIT (see [LICENSE](LICENSE))
