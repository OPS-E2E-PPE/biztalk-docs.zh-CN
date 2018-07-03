---
title: 反射 BizTalk 程序集时发生安全异常 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 301b85c7-8e67-482e-8666-67a91ca5c73d
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d07b1e5788ae696e94a3bbe326f2cfe79d1b76f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979926"
---
# <a name="a-security-exception-occurred-while-reflecting-a-biztalk-assembly"></a>反射 BizTalk 程序集时发生安全异常
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                                                                 |
| 产品版本 |                                                                                                                                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                                                                             |
|    事件 ID     |                                                                                                                                                                         0                                                                                                                                                                          |
|  事件源   |                                                                                                                                                                         0                                                                                                                                                                          |
|    组件    |                                                                                                                                                                         0                                                                                                                                                                          |
|  符号名称  |                                                                                                                                                                         0                                                                                                                                                                          |
|  消息正文   | 反射 BizTalk 程序集时发生安全异常"{0}"。 如果程序集位于共享网络文件夹中，则可能出现此问题。 若要更正此问题，请尝试以下项之一： 1。 将程序集及其依存关系复制到本地计算机。 2. 调整 .NET 配置运行时安全策略以允许访问。 |
  
## <a name="explanation"></a>解释  
 尝试在不具有正确 .NET 策略的网络共享上发布 BizTalk 程序集时，将发生此错误。  
  
## <a name="user-action"></a>用户操作  
 除了执行错误消息中列出的特定步骤之外，还应在本地复制程序集。 或编辑策略以向本地 Intranet 授予完全信任。  
  
 **使用代码访问安全策略工具 (Caspol.exe)**  
  
 您可以使用普通用户权限在用户级别为本地计算机上的文件夹授予信任。 要向网络位置授予信任，您必须具有管理员权限，并且可以在计算机级别更改安全策略。 计算机策略级别独立于用户策略级别，即使用户策略向 Intranet 区域授予完全信任，计算机策略级别也不会向 Intranet 区域授予完全信任。 策略级别必须一致。  
  
 **若要向本地文件夹授予完全信任**  
  
-   在 Visual Studio 命令提示符下键入以下命令：  
  
```  
caspol -u -ag All_Code -url   
C:\<FolderName>\<FolderName>\* FullTrust -n "<Name>" -d  
"<Description>"  
```  
  
 **若要向网络文件夹授予完全信任**  
  
-   在 Visual Studio 命令提示符下键入以下命令：  
  
```  
caspol -m -ag LocalIntranet_Zone -url   
\\<ServerName>\<FolderName>\* FullTrust -n "<Name>" -d   
"<Description>"  
```