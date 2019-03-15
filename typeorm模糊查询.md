**由于官网文档没有给出详细的说明，故在此做简要的文档记录**

如下所示：
```typescript
      async fuzzySearch(name: string){
      const postRepository = connection.getRepository(Post);
      return  await postRepository.createQueryBuilder("post")
                .where("post.title LIKE :param")
                .setParameters({
                    param: '%'+name+'%'
                })
                .orderBy("post.id", "ASC")
                .getMany();
      }
```
