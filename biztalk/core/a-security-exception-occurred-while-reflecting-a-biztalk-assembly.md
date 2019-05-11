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
ms.openlocfilehash: 3161593fb871e93852480f717216391daac67e7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362422"
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
|  消息正文   | 反射 BizTalk 程序集时发生安全异常"{0}"。 如果该程序集位于共享的网络文件夹中，可能会出现此问题。 若要更正此问题，请尝试以下项之一：1. 将程序集和其依赖项复制到本地计算机。 2. 调整.NET 配置运行时安全策略以允许访问。 |
  
## <a name="explanation"></a>解释  
 尝试发布不具有正确.NET 策略的情况下在网络共享上的 BizTalk 程序集时，将发生此错误。  
  
## <a name="user-action"></a>用户操作  
 除了错误消息中所述的特定步骤，将复制本地程序集。 或编辑策略以向本地 intranet 授予完全信任。  
  
 **使用代码访问安全策略工具 (Caspol.exe)**  
  
 在用户级别的普通用户权限与在本地计算机上，可以授予对文件夹的信任。 若要向网络位置授予信任，必须具有管理员权限并更改在计算机级别的安全策略。 计算机策略级别可独立于用户策略级别，即使用户策略，计算机策略级别不会授予完全信任权限的 Intranet 区域。 策略级别必须一致。  
  
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