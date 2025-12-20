Date: 2025-11-15
Tags: {
#F 
[[%TS]]
[[%Computer Science]]
}


# Prettify TS

```ts
// Lets say you have a pretty Complex Object 
// and are trying to understand while 
// hovering over it:

type ComplexType = {
	a: string;
	b: string;
} & Omit<
	{
		c: boolean;
	} & Record<"d", string[]>,
	"c"
>

// But when hovering over it you see this:

type ComplexType = {
	a: string;
	b: string;
} & Omit<{
		c: boolean;
} & Record<"d", string[]>, "c">

// Not really better, but there is a pretty
// good Trick:

type Prettify<T> = {
	[K in keyof T]: T[K];
} & {};

type ShowMe = Prettiy<ComplexType>;

//Which results in this while hovering:

type ShowMe= {
	a: string;
	b: number;
	d: string[];
}

//So much better.
```

## How does this work?


```ts
type Prettify<T> = {
	[K in keyof T]: T[K];
} & {}
```

```ts
[K in keyof T]: T[K];
```

>For every Key K in T, it takes the Type T[K] and builds a new Object, forcing TS to recalculate.
>The & {} is a Trick, to make sure that the Key is registered as new.
>Instead of showing the intern Constructor  (Omit<...> & ...), it shows the released Version.
