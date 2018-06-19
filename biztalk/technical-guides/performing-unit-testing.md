---
title: 执行单元测试 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40275d0b-b2ee-400c-9ef5-b9386ab0ae53
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a2084e2e46e3e984af2c5466c52862956dc8414
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009854"
---
# <a name="performing-unit-testing"></a>执行单元测试
单元测试的重点放在组件级别和基本上是通过/失败测试来验证按预期方式是否执行 BizTalk 解决方案的各个组件。 必须针对单元测试你的 BizTalk 解决方案的几个选项。  
  
## <a name="using-visual-studio"></a>使用 Visual Studio  
 单元测试功能是适用于 Visual Studio 2008 及更高版本。 有关适用于 Visual Studio 的测试功能的详细信息，请参阅[测试应用程序](http://go.microsoft.com/fwlink/?LinkId=159595)(http://go.microsoft.com/fwlink/?LinkId=159595)。  
  
 BizTalk Server 还提供了单元测试功能以使用户能够为架构、 映射和管道创建单元测试。 有关此功能的详细信息，请参阅[使用 BizTalk 服务器项目进行单元测试](http://go.microsoft.com/fwlink/?LinkId=158270)(http://go.microsoft.com/fwlink/?LinkId=158270)。  
  
> [!NOTE]  
>  Visual Studio 是用于单元测试如业务流程、 架构、 管道和管道组件的 BizTalk 项目非常有用。 BizTalk Server 提供测试类，你可以使用与 Visual Studio Team System 测试 BizTalk 项目。  
  
## <a name="using-non-microsoft-tools"></a>使用非 Microsoft 工具  
 单元测试 BizTalk 解决方案其他常用的以下两种工具**BizUnit**和**NUnit**。 **BizUnit**与 Visual Studio Team System 测试 Edition 无缝合作。 同样， **NUnit**测试可以轻松地修改，以便它们可以作为运行的是 Visual Studio Team System 测试 Edition 中。 有关这些工具的详细信息，请参阅[测试工具](~/technical-guides/tools-for-testing.md)。  
  
> [!NOTE]  
>  利用**BizUnit**和**NUnit**不支持由 Microsoft 和 Microsoft 则没有有关这些程序的适用性的保证。 使用这些程序完全需要您自担风险。  
  
## <a name="using-the-biztalk-server-sdk"></a>使用 BizTalk Server SDK  
 你可以执行单元测试的使用实用程序中提供的单个 BizTalk 项目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SDK。 下表提供了可用于单元测试的 SDK 中的实用程序的摘要：  
  
|**实用工具**|**用途**|  
|-----------------|-----------------|  
|AS2 发送方实用工具|使用此选项可将 AS2 消息发送到一台计算机上的网站。 此实用工具可模拟从单独的计算机发送 AS2 消息的过程。|  
|DSDump.exe|允许您转储文档架构结构，它是一个或多个 XSD 架构的内存中轻量表示形式，有或没有平面文件批注。 此工具在您获取诸如 $Root$0$3$2 这样的解析引擎错误并且需要对其进行解码时很有帮助。 $ 后的数字表示基于 0 的索引或记录，这些索引或记录显示在文档架构中。|  
|FFAsm.exe|运行平面文件组装器组件，通过模拟发送管道来直接调用它，从而允许您看到它如何将用户的 XML 文档序列化或组装到平面文件文档中。|  
|FFDasm.exe|运行平面文件拆装器组件，通过模拟接收管道来直接调用它，从而允许您看到它如何将用户的平面文件文档解析或拆装到一个或多个 XML 文档中。|  
|Pipeline.exe|运行发送或接收管道;接受一个或多个输入的文档和部件 XSD 架构和相关的信息;并生成后管道输出文档运行。 Pipeline.exe 不会访问[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，因此包含访问的 BizTalk Framework 汇编程序和反汇编程序组件的管道[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]期间执行数据库可能不受支持。|  
|XMLAsm.exe|运行 XML 组装器组件，通过模拟发送管道来直接调用它，从而允许您看到它如何将用户的 XML 文档序列化、组装或封装到输出 XML 文档中。|  
|XMLDasm.exe|运行 XML 拆装器组件，通过模拟接收管道来直接调用它，从而允许您看到它如何将用户的 XML 文档解析、拆装或解封装到一个或多个 XML 文档中。|  
  
 有关详细信息中提供的实用工具[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SDK，请参阅[SDK 中的实用程序](http://go.microsoft.com/fwlink/?LinkId=154387)(http://go.microsoft.com/fwlink/?LinkId=154387)。  
  
## <a name="see-also"></a>另请参阅  
 [测试工具](~/technical-guides/tools-for-testing.md)