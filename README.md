# NestJS request-context

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
