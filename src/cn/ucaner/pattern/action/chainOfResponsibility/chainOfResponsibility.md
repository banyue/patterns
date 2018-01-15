# 责任链模式

相信大家对责任链模式都很熟悉，多多少收都知道点，这次我们拿公司的财务报销来描述责任链模式，

> 使多个对象都有机会处理请求，从而避免了请求的发送者和接受者之间的耦合关系。将这些对象连成一条链，并沿着这条链传递该请求，直到有对象处理它为止。



| 类名                       | 描述          |
| ------------------------ | ----------- |
| Handler                  | 抽象处理者       |
| ManagerHandler           | 具体处理者（你的上司） |
| FinanceHandler           | 具体处理者（公司）   |
| BossHandler              | 具体处理者（公司老板） |
| ChainOfReponsibilityMain | 执行类（主方法—>你） |

假设  上司的能审批的金额level为 1，财务的level 为2，boss的level为3



责任链模式是一个运用递归思想来解决问题的模式，看代码就是像链表一样，优点是将请求和处理分开，请求者不必知道处理者是谁，处理者也可以不用知道请求的全貌，缺点也就比较明显：一是性能问题（遍历），二是调试不方便