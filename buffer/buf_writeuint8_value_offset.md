<!-- YAML
added: v0.5.0
changes:
  - version: v14.9.0
    pr-url: https://github.com/nodejs/node/pull/34729
    description: This function is also available as `buf.writeUint8()`.
  - version: v10.0.0
    pr-url: https://github.com/nodejs/node/pull/18395
    description: Removed `noAssert` and no implicit coercion of the offset
                 to `uint32` anymore.
-->

* `value` {integer} 要写入 `buf` 的数值。
* `offset` {integer} 开始写入之前要跳过的字节数。必须满足：`0 <= offset <= buf.length - 1`。**默认值:** `0`。
* 返回: {integer} `offset` 加上已写入的字节数。

将 `value` 写入到 `buf` 中指定的 `offset` 位置。
`value` 必须是无符号的 8 位整数。
当 `value` 不是无符号的 8 位整数时，行为是未定义的。

```js
const buf = Buffer.allocUnsafe(4);

buf.writeUInt8(0x3, 0);
buf.writeUInt8(0x4, 1);
buf.writeUInt8(0x23, 2);
buf.writeUInt8(0x42, 3);

console.log(buf);
// 打印: <Buffer 03 04 23 42>
```

