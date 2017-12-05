---
title: "BtarnConfig |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BTARN, exporting configuration data
- BTARN, BtarnConfig utility
- BtarnConfig utility
- BTARN, importing configuration data
ms.assetid: 8c95be2a-7df5-47fb-ae2d-64fa27e2811a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78ab62a86e97bf70e07629052a850b5aea2cee27
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="btarnconfig"></a>BtarnConfig
使用 BtarnConfig 实用工具可以将配置数据导入或导出 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 环境。 此处的配置数据是指用 BTARN 管理控制台设置的数据，包括流程配置设置、本组织、合作伙伴和协议。  
  
## <a name="location-in-sdk"></a>在 SDK 中的位置  
 \<*驱动器*\>\ Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本\>RosettaNet\SDK 快捷键  
  
## <a name="running-btarnconfig"></a>运行 BtarnConfig  
  
#### <a name="to-run-btarnconfig"></a>若要运行 BtarnConfig  
  
1.  打开命令提示符。  
  
2.  将移动到\<*驱动器*\>\ Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本\>Accelerator for RosettaNet\SDK\\。  
  
3.  在命令提示符处，键入**BtarnConfig**，键入相应的开关，然后按 enter 键。  
  
    > [!NOTE]
    >  下面的部分描述这些开关。  
  
## <a name="syntax-for-btarnconfig"></a>BtarnConfig 的语法  
 下面给出了用于启动此命令行工具的语法：  
  
### <a name="syntax-for-importing-configuration-data"></a>导入配置数据的语法  
  
```  
BTARNCONFIG /IMPORT <filename>.xml [/H] [/P] [/R] [/A]  
```  
  
### <a name="syntax-for-exporting-configuration-data"></a>导出配置数据的语法  
  
```  
BTARNCONFIG /EXPORT <filename>.xml [/H] [/P] [/R] [/A]  
```  
  
### <a name="syntax-description"></a>语法说明  
 下表描述了 BtarnConfig 实用工具使用的语法的各个部分。  
  
|语法|Description|  
|------------|-----------------|  
|\<*filename*.xml\>|要导入或导出的文件的完整路径。 如果你不提供的路径，BTARN 假定该路径\<*驱动器*\>\ Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本\>RosettaNet 快捷键\SDK。|  
|**/ 导入**|导入 XML 数据从\< *filename*.xml\>到 BTARN 配置。|  
|**/ 导出**|将 BTARN 配置导出到 XML 数据作为\< *filename*.xml\>。|  
|**/H**|导入或导出本组织配置数据。|  
|**/ P**|导入或导出合作伙伴配置数据。|  
|**/R**|导入或导出流程配置数据。|  
|**/ A**|导入或导出协议配置数据。|  
  
## <a name="remarks"></a>注释  
 如果未提供任何一种**/H**， **/P**， **/R**，或**/A**切换的 BtarnConfig 实用程序导入或导出的所有数据。 导出一个操作中的所有数据时，BtarnConfig 会将数据导出到 XML 文件中按以下顺序： 家庭组织、 合作伙伴、 过程配置和协议。  
  
 如果从中导入的文件存在结构性问题，BTARN 将会在架构验证阶段检测到错误，这样，在导入任何数据前，操作已失败。 如果出现其他错误，例如尝试导入重复的项目或 PIP/协议需要 HTTPS，则导入操作将失败。 但是，在操作失败时已导入的所有数据将保留在配置中。  
  
 你必须是 BizTalk 管理员才能使用 BtarnConfig 导入或导出配置数据。 如果你不是 BizTalk 管理员，则由于访问权限问题某些导入操作可能会失败。 但是，同一 BtarnConfig 命令中的其他导入操作可能会成功。  
  
## <a name="see-also"></a>另请参阅  
 [实用工具](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)