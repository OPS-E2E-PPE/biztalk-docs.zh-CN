---
title: "配置本地主机设置 （X12 交换设置） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c66c1e63-c654-4ccb-b424-34c06f1ce94e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10172c700d8b3d8d2039e46f28d24ff39ba93aac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-local-host-settings-x12-interchange-settings"></a>配置本地主机设置（X12-交换设置）
本地主机设置控制如何处理 EDI 交换。 此页上的设置可以分为两个类别：接收方设置（用于传入交换）和发送方设置（用于传出交换）。 在接收方的设置中，可以指定传入的批是拆分为事务集还是保留。 如果保留，可以指定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在发生错误时是否挂起交换或事务集。 在发送方的设置中，您可以指定如何为传出消息生成控制编号。  
  
> [!NOTE]
>  此处所述的设置同样适用于 HIPAA 交换。  
  
> [!IMPORTANT]
>  以下属性上将禁用**A 方-> 方 B**单向协议选项卡，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**复选框 a 方。  
>   
>  -   下的所有属性**发件人设置**部分。  
>   
>  同样，将以下属性禁用中相同页面上**B 方-> A 方**选项卡上，如果创建 a 方。 时选中复选框  
>   
>  -   下的所有属性**接收方设置**部分。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-local-host--receivers-settings"></a>配置本地主机 – 接收方设置  
  
1.  创建 X12 编码协议中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。 若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**交换设置**部分中，单击**本地主机设置**。  
  
3.  清除**路由 ACK 发送管道请求-响应接收端口**返回由单独的确认发送端口。 如果将该属性保留为选中状态，则会在与双向请求-响应接收端口关联的发送端口上返回确认。  
  
4.  若要指定确认中使用的事务集控制编号的范围，请输入中的值**ACK 控制编号 (ST02)**字段。 请在中间两个字段中输入一个数值，而为前缀和后缀字段输入字母数字值（如果需要）。 中间字段是必填字段，包含控制编号的最小值和最大值；前缀和后缀可选。 所有三个字段的最大长度均为 9 个字符。  
  
     若要重置当前事务集控制编号的最小值，请单击**重置**。 检查**重置为下限超出界限时**来将控制编号重置为较低的限制，一旦已超过最大值。  
  
5.  选择**屏蔽上下文属性中的安全/授权/密码信息**复选框以启用屏蔽上下文属性，以防止信息中的授权/密码安全信息 （ISA2 和 ISA4 字段）泄露。  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 收到消息时，它将 ISA 标头升级到消息的上下文中。 如果不屏蔽，具有管理权限的任何人都可获取此上下文中的安全信息。 若要屏蔽此信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]替换信息的每个字符 **#** 字符。 这是一个单向过程：  **#** 字符无法转换为实际字符。  
  
6.  在**入站批处理选项**下拉列表中，执行以下操作：  
  
    1.  选择默认选项**将交换拆分为事务集-出错时暂停事务集**指定 BizTalk Server 应分析每个事务集到单独的 XML 文档将交换中。 然后，BizTalk Server 将相应的信封应用到事务集，并且将事务集文档路由至 MessageBox。 选择此选项后，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将仅挂起这些交换集。  
  
    2.  选择**将交换拆分为事务集-出错时暂停交换**指定 BizTalk Server 应分析每个事务集到单独的 XML 文档将交换中。 然后，BizTalk Server 将相应的信封应用到事务集，并且将事务集文档路由至 MessageBox。 选择此选项后，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将挂起整个交换。  
  
    3.  选择**保留交换-出错时暂停交换**指定 BizTalk Server，应保留交换不变，以创建 XML 文档是否为整个批处理的交换。 选择此选项后，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将挂起整个交换。  
  
    4.  选择**保留交换-出错时暂停事务集**指定 BizTalk Server，应保留交换不变，以创建 XML 文档是否为整个批处理的交换。 使用此选项时，如果交换中的一个或多个事务集未通过验证，BizTalk Server 将会挂起仅这些事务集，同时继续处理所有其他事务集。  
  
        > [!NOTE]
        >  如果你选择**保留交换-出错时暂停交换**或**保留交换-出错时暂停事务集**，交换、 组和事务设置段属性 (确定如何 BizTalk Server 将创建传出交换的 ISA，GS 和 ST 标头） 不适用。 被保留的交换中存在的交换、组和事务集标头将在发送管道对其执行发送前的相关处理时予以保留。  
  
### <a name="to-configure-local-host--senders-settings"></a>配置本地主机 – 发送方设置  
  
1.  有关**交换控制编号 (ISA13)**，输入的用于 BizTalk Server 中生成传出交换的交换控制编号的值的范围。 输入一个最小为 1、最大为 999999999 的数值。 此字段是必需字段。  
  
     若要将控制编号重置为指定的最小值，请单击**重置**按钮。 检查**重置为下限超出界限时**自动重置的最小值如果超出最大值。  
  
2.  有关**组控制编号 (GS06)**，输入的 BizTalk Server 应该用于组控制编号的数字范围。 输入一个最小为 1 个字符最大为 9 个字符的数值。 这是必填字段。  
  
     若要将组控制编号重置为指定的最小值，请单击**重置**按钮。 检查**重置为下限超出界限时**自动重置的最小值如果超出最大值。  
  
3.  有关**事务集控制编号 (ST02)**，单击**应用新的 ID** ，然后输入可选前缀和后缀的一系列的必填的中间字段，数字值和字母数字值。 所有四个字段的最大长度为 9 个字符。  
  
     若要重置当前事务集控制编号的最小值，请单击**重置**。 选择**重置为下限超出界限时**来将控制编号重置的最小值为，如果尚未超过最大值。  
  
4.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置交换设置 (X12)](../core/configuring-interchange-settings-x12.md)