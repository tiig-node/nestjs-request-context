# NestJS request-context

[![CI](https://github.com/npkgdev/nestjs-request-context/actions/workflows/ci.yml/badge.svg)](https://github.com/npkgdev/nestjs-request-context/actions/workflows/ci.yml)
[![GitHub release](https://img.shields.io/github/v/release/npkgdev/nestjs-request-context.svg)](https://GitHub.com/npkgdev/nestjs-request-context/releases/)
[![GitHub license](https://img.shields.io/github/license/npkgdev/nestjs-request-context.svg)](https://github.com/npkgdev/nestjs-request-context/blob/main/LICENSE)

Workaround for getting Request information from a non request-scoped service in NestJs.

# Usage

Full example in `test` folder

```typescript
@Module({
  imports: [RequestContextModule], // automatically binds the proper middleware
  providers: [...],
  controllers: [..],
})
export class AppModule {}
```

Accessing request from service
```typescript
@Injectable()
export class SingletonService {

  getRequestId() {
    const req: Request = RequestContext.currentContext.req;
    return req.requestId;
  }

}
```
