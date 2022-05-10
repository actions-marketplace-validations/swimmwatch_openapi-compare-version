# openapi-compare-version
A GitHub Action for comparing OpenAPI specifications version.

## Usage
```yml
- name: "Compare OpenAPI specifications version"
  id: compare_res
  uses: swimmwatch/openapi-compare-version@v1.0.1
  with:
    current-spec: "old_spec.json"
    new-spec: "new_spec.json"
- name: "Output result"
  if: ${{steps.compare_res.outputs.is-diff-version}} == 'true'
  run: echo "Version is different"
```

## Options
The following input variables options can/must be configured:

|Input variable|Necessity|Description|Default|
|----|----|----|----|
|`current-spec`|Required|Current specification path||
|`new-spec`|Required|New specification path||

## Outputs
- `is-diff-version`: Difference version state (`true` or `false`).

## License
openapi-compare-version is licensed under the [MIT License](LICENSE).