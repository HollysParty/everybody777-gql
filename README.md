# everybody777 graphql schema

이 저장소에는 아래 내용을 포함합니다.

- GraphQL Schema
- Schema로부터 typescript/kotlin 타입 정의를 자동 생성하는 설정/도구

## Requirements

- NodeJS v12 이상
- yarn

## Package Install

`yarn install`

## 자동 생성

프로젝트 루트에서 `yarn gen` 명령어를 사용하면 `/gen` 폴더에 타입 정의하는 파일이 생성됩니다.

예를 들어 graphql schema에 아래와 같은 타입 정의가 있다고 하면

```graphql
type Tile {
  order: Int!
  sketchUrl: String!
}
```

typescript로는 다음과 같은 정의가 생성됩니다.

```typescript
export type Scalars = {
  ID: string;
  String: string;
  Boolean: boolean;
  Int: number;
  Float: number;
};

export type Tile = {
  __typename?: "Tile";
  order: Scalars["Int"];
  sketchUrl: Scalars["String"];
};
```

kotlin으로는 다음과 같은 정의가 생성됩니다.

```kotlin
data class Tile(
    val order: Int,
    val sketchUrl: String
)
```
