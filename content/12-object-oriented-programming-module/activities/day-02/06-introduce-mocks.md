+++
title = "06.  Introduce Mocks 👩‍🏫🧑‍🏫"
weight = 6
tags = ["oop"] 
+++

### logger.test.js
```js
const Logger = require("../logger");

const colors = {
  black: "\x1b[30m",
  red: "\x1b[31m",
  green: "\x1b[32m",
  yellow: "\x1b[33m",
  blue: "\x1b[34m",
  magenta: "\x1b[35m",
  cyan: "\x1b[36m",
  white: "\x1b[37m"
};

describe("Logger", () => {
  describe("colors", () => {
    it("should print in black", () => {
      const log = new Logger();
      const message = "Hello world!";
      const mock = jest.spyOn(console, "log");
      mock.mockImplementation(() => {});

      log.black(message);

      expect(mock).toBeCalledWith(colors.black, message);

      mock.mockRestore();
    });

    it("should print in red", () => {
      const log = new Logger();
      const message = "Hello world!";
      const mock = jest.spyOn(console, "log");
      mock.mockImplementation(() => {});

      log.red(message);

      expect(mock).toBeCalledWith(colors.red, message);

      mock.mockRestore();
    });

    it("should print in green", () => {
      const log = new Logger();
      const message = "Hello world!";
      const mock = jest.spyOn(console, "log");
      mock.mockImplementation(() => {});

      log.green(message);

      expect(mock).toBeCalledWith(colors.green, message);

      mock.mockRestore();
    });

    it("should print in yellow", () => {
      const log = new Logger();
      const message = "Hello world!";
      const mock = jest.spyOn(console, "log");
      mock.mockImplementation(() => {});

      log.yellow(message);

      expect(mock).toBeCalledWith(colors.yellow, message);

      mock.mockRestore();
    });

    it("should print in blue", () => {
      const log = new Logger();
      const message = "Hello world!";
      const mock = jest.spyOn(console, "log");
      mock.mockImplementation(() => {});

      log.blue(message);

      expect(mock).toBeCalledWith(colors.blue, message);

      mock.mockRestore();
    });

    it("should print in magenta", () => {
      const log = new Logger();
      const message = "Hello world!";
      const mock = jest.spyOn(console, "log");
      mock.mockImplementation(() => {});

      log.magenta(message);

      expect(mock).toBeCalledWith(colors.magenta, message);

      mock.mockRestore();
    });

    it("should print in cyan", () => {
      const log = new Logger();
      const message = "Hello world!";
      const mock = jest.spyOn(console, "log");
      mock.mockImplementation(() => {});

      log.cyan(message);

      expect(mock).toBeCalledWith(colors.cyan, message);

      mock.mockRestore();
    });

    it("should print in white", () => {
      const log = new Logger();
      const message = "Hello world!";
      const mock = jest.spyOn(console, "log");
      mock.mockImplementation(() => {});

      log.white(message);

      expect(mock).toBeCalledWith(colors.white, message);

      mock.mockRestore();
    });
  });
});
```


### index.js
```js
const Logger = require("./logger");

const log = new Logger();

log.red("We can write to the console in different colors!");

log.blue("We just need to provide an additional argument to the console.log method!");

log.magenta("The first argument console.log needs is an 'ANSI Escape Code'");

log.green("You can look these up at https://en.wikipedia.org/wiki/ANSI_escape_code#Colors");

log.yellow("But they're just codes that represent different colors");

log.cyan("The second argument console.log should receive is the message to be printed");

```

### logger.js
```js
const Logger = require("./logger");

const log = new Logger();

log.red("We can write to the console in different colors!");

log.blue("We just need to provide an additional argument to the console.log method!");

log.magenta("The first argument console.log needs is an 'ANSI Escape Code'");

log.green("You can look these up at https://en.wikipedia.org/wiki/ANSI_escape_code#Colors");

log.yellow("But they're just codes that represent different colors");

log.cyan("The second argument console.log should receive is the message to be printed");
```