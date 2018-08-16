---
title: ImportParties 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87d43e2c-401c-4450-ad9b-2528086b99e4
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6c25b913b6479b857fb7cee4aec10e6984f2195
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998534"
---
# <a name="importparties-command"></a>ImportParties 命令
从导入企业到企业参与方和协议配置数据库中的源 XML 绑定文件而无需导入的任何应用程序项目。 有关详细信息，请参阅**备注**本主题中。  

> [!IMPORTANT]
> 此命令将新开头**[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**，和任何更高版本。
> 
> [!NOTE]
>  绑定文件中生成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不具有指定的应用程序。 它们被导入到默认的应用程序中。  
  
## <a name="usage"></a>用法  
  **BTSTask ImportParties-源**:*值*[**-ExcludeEdiFallbackSettings**] [**-Server**:*值*] [**-数据库**:*值*]
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|ReplTest1|  
|---|---|---|  
|**-源** | Required | 要读取的 XML 绑定文件的路径和文件名称。|
|**-ExcludeEdiFallbackSettings** | 可选 | 如果指定，系统会从绑定文件中排除 edi 回退 （x12 和 edifact） 设置。  |
| **-服务器** | 可选 | 承载 BizTalk 配置数据库的 SQL server 的名称。 |
| **-数据库** | 可选 | BizTalk 配置数据库的名称。 |

## <a name="sample"></a>示例
  `BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

## <a name="remarks"></a>Remarks
如果绑定文件也具有应用程序项目，然后它们将不导入。 导入仅参与方和协议。