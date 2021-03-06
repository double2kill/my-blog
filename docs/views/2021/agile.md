---
title: 敏捷开发
date:   2021-02-25 15:00:31
tags:
 - 敏捷开发
categories:
 - 项目管理
---

敏捷开发（agile development）是非常流行的软件开发，现在的开发已经离不开敏捷开发了。据统计，已经有90%用上了敏捷开发。今天就来谈论一下我对敏捷开发的认识。
<!-- more -->

# 经济学角度看敏捷开发

通常我们谈到它，通常是这么说的，“敏捷开发可以快速响应用户需求，快速发现问题，快速试错，相比于瀑布流，一个阶段做完才可以做下个阶段”。我总感觉很奇怪，为什么有人会不用敏捷开发，会去用瀑布流那么死板？直到我自己做了一个私人项目，我极力的想找甲方要详细的需求，但是甲方永远都给不出任何细节的需求，要到的总是那句话“如果都要我来想，那要你干什么？”

面对这种情况我们通常的做法，那就是和甲方约定需求，对需求签字画押，这种文档通常就是“合同”，“立项申请书”等等。有了这些，作为乙方的我们就可以只需要做到字面上的必完成项（就能挣到约定的金钱）。在公司内部，分工做事已经是必然的事情，每个人都即是甲方也是乙方，这也就是为什么听到这种声音 - “需求没有确定，我们不做开发”，“开发没有全部做好，我们没办法测试”。这些就是瀑布流的雏形。

所以我们应该怎么做？对外瀑布流，对内做到敏捷。

# 关键点
## 没有明确的分工

有明确的分工，那么公司的流程就会趋于瀑布流，反之大家会趋于敏捷。所以敏捷开发首要任务就是消除分工，敏捷开发的角色只有两种，一种是 scrum master, 另一种是 team 成员。PM/开发/QA是一条船上的，PM/QA 也是可以懂一点技术细节的，开发也可以增加产品质量的思考，team的事情其实是不可分割的，都是为了完成预定的需求。

## 快速迭代

1. Scrum 流程上限制时间，一个 Sprint 周期只有一个星期或者两个星期。这样在一定程度上可以限制 Sprint 的任务，让大家更关注 Sprint 内的事情。
2. 促进需求拆分，只有把需求细化，把一个 13 分的 User Story 拆分成好几个 1 分、2 分的任务，这样在 Sprint Planning 时候才可以做计划。
3. 促进需求的完善，有些问题只有做了才能知道下一步该怎么做，不然可能会互相等，PM希望开发进行调研，开发希望需求明确。


## 快速试错

1. 促进自动化测试的完善，只有每个 sprint都有一定的回归测试，才能保证后期不被回归的 bug 淹没，慢慢把一些可重复性的测试工作交给自动化测试，可以在改动的时候更有信心。
2. 促进 CI/CD 的完善。代码到生产环境的速度足够快，足够稳定，才可以快速试错，部署的所有操作都代码化，已减少人工的干预。
3. Retrospective meeting, 定期有回顾会，大家都认真分析做的好和方面和可以改善的方面，有利于之后工作的开展。

## 测试方式的选择

1. 团队讨论的最终选择的测试方式就是最合适的。
2. 理解每种测试（E2E 测试/集成测试/单元测试/手工测试）的优缺点，并且让团队的认识保持一致。测试覆盖的范围可以交叉，但不能少。比如出现 QA 认为集成测试的覆盖模块大于实际测到的模块，而没有进行一个全模块的测试。

# 总结

敏捷开发是一个很不错的开发管理思维方式，真的没想到可以基于这种思维衍生出这么多有意义做法。

# 更多资料
[阮一峰-敏捷开发入门教程
](http://www.ruanyifeng.com/blog/2019/03/agile-development.html)