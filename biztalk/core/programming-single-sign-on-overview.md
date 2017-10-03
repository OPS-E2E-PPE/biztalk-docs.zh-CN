---
title: "编程单一登录概述 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a0a3978-cdbf-4703-9d1d-23e0f4923c9c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5f8ffa7463e4c1fbdd7231cf87abea751fea3d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="programming-single-sign-on-overview"></a>编程单一登录概述
依赖于多个不同应用程序的业务流程可能需要处理多个不同的安全域。 访问 Microsoft Windows 操作系统上的应用程序可能需要一组安全凭据，而访问 IBM 大型机上的应用程序可能需要不同的凭据。 处理如此多的凭据对于用户而言并非易事，而这也给流程自动化带来了更大的挑战。 若要解决此问题，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包括企业单一登录 (SSO)。 通过 SSO，可将 Windows 用户 ID 映射到非 Windows 用户凭据。 此服务可以简化使用不同系统中的应用程序的业务流程。  
  
 若要使用 SSO，管理员需要定义关联的应用程序，每个关联应用程序均表示一个非 Windows 的系统或应用程序。 关联应用程序可以是在 IBM 大型机上运行的客户信息控制系统 (CICS) 应用程序、UNIX 上运行的 SAP ERP 系统或任何其他类型的软件。 以上每种应用程序都拥有自己的验证机制，因此它们也都需要自己的唯一凭据。  
  
 SSO 存储了用户的 Windows 用户 ID 与一个或多个关联应用程序的关联凭据之间的加密映射。 这些关联的凭据对存储在 SSO 数据库中。 SSO 以两种方式使用 SSO 数据库。 第一种方法，调用*Windows 启动单一登录*，使用用户 ID 来确定用户有权访问的关联的应用程序。 例如，某个 Windows 用户帐户所关联的凭据可能授予对远程 AS/400 服务器上运行的 DB2 数据库的访问权。 第二种方法，调用*主机启动的单一登录*，按相反的顺序的作用： 确定哪些远程应用程序有权访问的指定的用户 ID，并转到与该帐户的特权。 例如，某个远程应用程序所关联的凭据可能授予对 Windows 网络具有管理权限的用户帐户的访问权。  
  
 请注意，SSO 还包含执行不同操作的管理工具。 例如，对 SSO 数据库执行的所有操作都需要进行审核，管理员可以通过企业单一登录提供的工具来监视这些操作并设置不同的审核级别。 管理员还可以利用其他工具来禁用特定的关联应用程序、为用户打开和关闭单独的映射以及实现其他功能。 此外，最终用户可以通过一个客户端程序配置自己的凭据和映射。  
  
 针对单一登录的管理要求之一是本地系统必须知道登录远程系统所需的凭据。 同样，远程系统也必须知道登录您的本地系统所需的凭据。 因此，在更新凭据（如更新本地计算机上的密码）时，还必须将所做的更改通知给远程系统。 将密码同步的企业的组件设计被称作*密码同步适配器*。  
  
## <a name="in-this-section"></a>本节内容  
 [单一登录接口](../core/single-sign-on-interface.md)  
  
 [单一登录在应用程序](../core/single-sign-on-applications.md)  
  
 [在编程上单一登录之前应该知道哪些内容](../core/what-you-should-know-before-programming-single-sign-on.md)  
  
 [受支持的平台上单一登录](../core/supported-platforms-for-single-sign-on.md)