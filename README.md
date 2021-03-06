# Koa Starter 

## Features â¨

- Koa2
- TypeScript
- ESM
- Koa-Router

## Getting Started ð

```bash
# install deps
pnpm i
# start app
pnpm start
```

The koa web servcice will listen on port 3000 default.

If you want to change the default listen port, Please go to `.env` file.

## How it works? ð
<details>
<summary>æ¥çè£é¥°å¨ç¸å³ä¿¡æ¯</summary>

### å¨ koa ä¸­ä½¿ç¨è£é¥°å¨

æä»¬ç¥éï¼å¯ä»¥ä½¿ç¨ `koa-router` æ¥æè¿°ä¸ä¸ªè·¯ç±ï¼

```ts
router.get('/', (ctx) => {})
```

èè£é¥°å¨è¦åçäºæï¼å¶å®å°±æ¯å° `@GET` ä»¥åå¶å½æ°ï¼è½¬æ¢ä¸ºä¸æçåæ³

æ ¸å¿çä»£ç å¶å®å°±æ¯ï¼
```ts
// ä»åæ°æ®ä¸­è·å pathãmethodãhandler
const path: string = Reflect.getMetadata('path', target.prototype, key)
const method: Methods = Reflect.getMetadata('method', target.prototype, key)
const handler: any = target.prototype[key]
const middlewares: any[] = Reflect.getMetadata('middlewares', target.prototype, key) || []
if (path && method) {
  const prefixCoverPath = prefix === '/' ? path : `${prefix}${path}`
  // è½¬æ¢ä¸ºè¿ä¸ª router['GET']('xxxxxx') çåæ³
  if (middlewares.length)
    router[method](prefixCoverPath, ...middlewares, handler)
  else
    router[method](prefixCoverPath, handler)

}
```

### æ³¨æ

æ ¸å¿çé»è¾å°±æ¯éè¿è·å class ä¸­çææçæ¹æ³ï¼ç¶åéåï¼éè¿è£é¥°å¨æè½½å° `koa-router` ä¸­
ä¸è¿ç±äºç¨å°äº `class.prototype` è·åææçå®ä¾æ¹æ³ï¼æä»¥ï¼å¦æ class ä¸­çæ¹æ³æ¯éææ¹æ³ï¼é£ä¹å°±ä¼æ¶åä¸å°ï¼èä¸åªè½å¨ `tsconfig.compilerOptions.target = 'es5'` çæ¶åæè½ç¨ï¼å ä¸º es5 å®ç° class æ¯ç´æ¥å°å®ä¾å±æ§åæ¹æ³æè½½å°äº object ä¸é¢
</details>

## References ð

- [koa-utils](https://github.com/TTiip/koa-utils)
