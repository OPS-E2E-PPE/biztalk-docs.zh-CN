---
title: 编程单一登录概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a0a3978-cdbf-4703-9d1d-23e0f4923c9c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db2a87641ecb9df939678a887b1dfd95b2da3806
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255130"
---
# <a name="programming-single-sign-on-overview"></a>编程单一登录概述
业务流程依赖于多个不同的应用程序很可能面临着挑战，处理多个不同的安全域。 访问 Microsoft Windows 操作系统上的应用程序可能需要一组安全凭据，而访问 IBM 大型机上的应用程序可能需要不同的凭据。 对于用户，处理此而言并非易事的凭据，也可能会带来更大的挑战用于自动执行流程。 若要解决此问题，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包含企业单一登录 (SSO)。 SSO 允许将 Windows 用户 ID 映射到非 Windows 用户凭据。 此服务可以简化在不同系统使用应用程序的业务流程。  
  
 若要使用 SSO，管理员需要定义关联应用程序，其中每个表示非 Windows 系统或应用程序。 关联应用程序可能在 IBM 大型机，UNIX 或任何其他类型的软件运行的 SAP ERP 系统运行的客户信息控制系统 (CICS) 应用程序。 每个这些应用程序都有其自身的机制进行身份验证，并因此每个都需要其自己唯一的凭据。  
  
 SSO 将存储用户的 Windows 用户 ID 和一个或多个关联应用程序的关联的凭据之间的加密的映射。 这些链接的对存储在 SSO 数据库中。 SSO 以两种方式使用 SSO 数据库。 第一种方法，称为*Windows 启动单一登录*，使用用户 ID 来确定用户有权访问的关联应用程序。 例如，Windows 用户帐户关联的可能授予对上远程运行的 DB2 数据库访问权限的凭据 / 400 服务器。 第二种方法，称为*主机启动的单一登录*，方式相反： 确定哪些远程应用程序有权访问指定的用户 ID，并使用该帐户的权限。 例如，远程应用程序关联的可能授予对 Windows 网络具有管理权限的用户帐户访问权限的凭据。  
  
 请注意，SSO 还包含管理工具执行各种操作。 SSO 数据库执行的所有操作进行都审核;例如，工具会提供，使管理员能够监视这些操作并设置不同的审核级别。 其他工具使管理员能够禁用特定的关联应用程序、 打开和关闭单独的映射是用户，以及执行其他功能。 此外，还有使最终用户能够配置其自己的凭据和映射的客户端程序。  
  
 单一登录的管理要求之一是您的本地系统必须知道登录远程系统所需的凭据。 同样，在远程系统必须知道您的本地系统上的凭据。 因此，当更新你的凭据，例如在本地计算机上更新你的密码时，必须通知远程系统已完成操作。 将密码同步整个企业内的组件在设计称为*密码同步适配器*。  
  
## <a name="in-this-section"></a>本节内容  
 [单一登录界面](../core/single-sign-on-interface.md)  
  
 [单一登录应用程序](../core/single-sign-on-applications.md)  
  
 [对单一登录进行编程前的需知](../core/what-you-should-know-before-programming-single-sign-on.md)  
  
 [支持的单一登录平台](../core/supported-platforms-for-single-sign-on.md)