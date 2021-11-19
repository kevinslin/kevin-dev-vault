---
id: 87fa96b8-08ce-4756-a645-9b34a7899e20
title: Ts Ed
desc: ''
updated: 1611114496057
created: 1611113817070
---


## Summary
- A Node.js and TypeScript Framework on top of Express. It provides a lot of decorators and guidelines to write your code. 

## Quickstart
- source: https://github.com/TypedProject/tsed
  license: MIT

```ts
import {Inject} from "@tsed/di";
import {Summary} from "@tsed/swagger";
import {Controller, Get, QueryParams, PathParams, Delete, Post, Required, BodyParams, Status, Put, Returns, ReturnsArray} from "@tsed/common";
import {BadRequest} from "@tsed/exceptions";
import {UsersService} from "../services/UsersService";
import {User} from "../models/User"; 

@Controller("/users")
export class UsersCtrl {
  @Inject()
  usersService: UsersService;

  @Get("/:id")
  @Summary("Get a user from his Id")
  @Returns(User)
  async getUser(@PathParams("id") id: string): Promise<User> {
     return this.usersService.findById(id);
  }

  @Post("/")
  @Status(201)
  @Summary("Create a new user")
  @Returns(User)
  async postUser(@Required() @BodyParams() user: User): Promise<User> {
    return this.usersService.save(user);
  }

  @Put("/:id")
  @Status(201)
  @Summary("Update the given user")
  @Returns(User)
  async putUser(@PathParams("id") id: string, @Required() @BodyParams() user: User): Promise<User> {
    if (user.id !== id) {
      throw new BadRequest("ID mismatch with the given payload")
    }

    return this.usersService.save(user);
  }
  
  @Delete("/:id")
  @Summary("Remove a user")
  @Status(204)
  async deleteUser(@PathParams("id") @Required() id: string ): Promise<User> {
     await this.usersService.delete(user);
  }
  
  @Get("/")
  @Summary("Get all users")
  @ReturnsArray(User)
  async findUser(@QueryParams("name") name: string){
    return this.usersService.find({name});
  }
}
```

## Sources
- https://github.com/TypedProject/tsed
- https://medium.com/swlh/introduction-to-ts-ed-b391c854947a
