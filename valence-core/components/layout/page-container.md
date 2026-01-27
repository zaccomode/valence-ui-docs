---
description: 'Last updated: 3.0.0 (04/07/2024)'
---

# Page Container

The Page Container is a convenience component that combines an [Overflow Container](overflow-container.md) with a [Flex Center](flex/flex-center.md) to create a standard page layout. It provides a scrollable area with centered, width-constrained content.

## Usage

```tsx
import { PageContainer, Text, Title } from "@valence-ui/core";

function MyPage() { 
    return ( 
        <PageContainer>
            <Title>My Page</Title>
            <Text>
                This content is centered and constrained to a maximum width.
            </Text>
        </PageContainer>
    )
}
```

### Custom inner width

By default, the inner content is constrained to `min(100%, 700px)`. You can customize this:

```tsx
import { PageContainer, Text } from "@valence-ui/core";

function MyPage() { 
    return ( 
        <PageContainer
            innerWidth="min(100%, 1000px)"
        >
            <Text>
                Wider content area!
            </Text>
        </PageContainer>
    )
}
```

### Exempt content

The `exemptContent` prop allows you to add content that sits outside the centered area, useful for full-width headers or banners:

```tsx
import { PageContainer, Header, Text, Title } from "@valence-ui/core";

function MyPage() { 
    return ( 
        <PageContainer
            exemptContent={
                <Header>
                    <Title>Full-width Header</Title>
                </Header>
            }
        >
            <Text>
                This content is centered below the header.
            </Text>
        </PageContainer>
    )
}
```

### Custom overflow container props

You can pass props to the underlying Overflow Container:

```tsx
import { PageContainer, Text } from "@valence-ui/core";

function MyPage() { 
    return ( 
        <PageContainer
            overflowContainerProps={{
                height: "50vh",
                direction: "vertical",
            }}
        >
            <Text>
                Custom scroll container!
            </Text>
        </PageContainer>
    )
}
```

***

## Props

_Extends_ [_`FlexCenterProps`_](flex/flex-center.md#props)_._

<table data-full-width="true"><thead><tr><th width="220">Property</th><th width="250">Type</th><th>Description</th></tr></thead><tbody><tr><td>exemptContent</td><td><code>ReactNode</code></td><td>Content to render outside the centered area, above the main content.</td></tr><tr><td>overflowContainerProps</td><td><a href="overflow-container.md#props"><code>OverflowContainerProps</code></a></td><td>Optional props to pass to the Overflow Container.</td></tr></tbody></table>
