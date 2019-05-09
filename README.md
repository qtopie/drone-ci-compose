# drone-ci-compose

- [中文](README.zh.md)



## Commons Problems
- Webhook not working
Modify webhook `localhost` to `drone-server`, eg the push url should be like this: `http://drone-server/hook`

when refer env variables you should use $${variable} instead of ${variable}
