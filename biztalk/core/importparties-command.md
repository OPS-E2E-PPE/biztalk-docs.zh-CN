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
ms.openlocfilehash: 09e59f51aa6d99fbd9b1351087a403350cc22a1f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382214"
---
# <a name="importparties-command"></a>ImportParties 命令
从导入企业到企业参与方和协议配置数据库中的源 XML 绑定文件而无需导入的任何应用程序项目。 有关详细信息，请参阅**备注**本主题中。  

> [!IMPORTANT]
> 此命令将新开头**[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**，和任何更高版本。
> 
> [!NOTE]
>  绑定文件中生成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不具有指定的应用程序。 它们是导入到默认应用程序。  
  
## <a name="usage"></a>用法  
  **BTSTask ImportParties -Source**:*value* [**-ExcludeEdiFallbackSettings**] [**-Server**:*value*] [**-Database**:*value*]
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|ReplTest1|  
|---|---|---|  
|**-Source** | Required | 要读取的 XML 绑定文件的路径和文件名称。|
|**-ExcludeEdiFallbackSettings** | 可选 | 如果指定，系统会从绑定文件中排除 edi 回退 （x12 和 edifact） 设置。  |
| **-Server** | 可选 | 承载 BizTalk 配置数据库的 SQL server 的名称。 |
| **-Database** | 可选 | BizTalk 配置数据库的名称。 |

## <a name="sample"></a>示例
  `BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

## <a name="remarks"></a>备注
如果绑定文件也具有应用程序项目，然后它们将不导入。 导入仅参与方和协议。