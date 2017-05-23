# opentracing-awsxray

This repository is a place to document mappings between [opentracing](https://opentracing.io) and [AWS X-Ray](https://aws.amazon.com/xray/), independent of language.

## Project Goals

In addition to providing Tracer implementations for X-Ray, the tracing should allow interoperability with traces passing through both native X-Ray and Opentracing.

This means both that traces should cross boundaries and also that within one process Opentracing traces will interoperate with AWS resource calls that natively trace using X-Ray, such as DynamoDB.

## Terminology Mapping

<table>
  <tr><th>Opentracing</th><th>AWS X-Ray</th></tr>
  <tr><td>Trace</td><td>Trace</td></tr>
  <tr><td>Span</td><td>Segment</td></tr>
  <tr><td>"ChildOf" Span</td><td>Subsegment</td></tr>
  <tr><td>"FollowsFrom" Span</td><td>???</td></tr>
  <tr><td>Baggage Items</td><td>Annotation (Indexed key-value pairs)</td></tr>
  <tr><td>Baggage Items</td><td>Metadata (Non-indexed key-value pairs, incudes structured data)</td></tr>
</table>
