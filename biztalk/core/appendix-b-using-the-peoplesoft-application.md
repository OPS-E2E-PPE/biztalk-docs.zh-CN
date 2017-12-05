---
title: "附录 b： 使用 PeopleSoft 应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PeopleSoft, using
- using PeopleSoft application
ms.assetid: 36475836-1d23-4bb4-a3c1-cdd3fff28476
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbe0bba08421360364fb668be9ae4d980d7a54d8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="appendix-b-using-the-peoplesoft-application"></a>附录 b： 使用 PeopleSoft 应用程序
本部分介绍使用 PeopleSoft 的不同区域，以便可以在业务流程测试中发挥作用。  
  
 将 PeopleSoft 用于接收端口时，使用 PeopleTools 来创建 XML 文档。 与 PeopleSoft 交互没有特殊的要求。 事件，你必须能够访问**http\\\\:\<主机\>:\<端口\>**以侦听来自 PeopleSoft 事件。 如果您无法使用主机和端口，则可以通过配置 PeopleSoft Integration Broker 设置特定的 HTTP 主机和端口。  
  
 若要完成测试 PeopleSoft 接收端口，[生成 XML 或架构中 PeopleSoft](../core/generating-xml-or-schema-in-peoplesoft.md)讨论如何通过更改 PeopleSoft 环境中的一些东西触发 PeopleSoft 事件。 此更改将激活发送到文件夹（在要监视的业务流程中设置）中的 XML 文件。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [在 PeopleSoft 中生成 XML 或架构](../core/generating-xml-or-schema-in-peoplesoft.md)  
  
-   [创建 PeopleSoft HTTP 主机和端口](../core/creating-a-peoplesoft-http-host-and-port.md)