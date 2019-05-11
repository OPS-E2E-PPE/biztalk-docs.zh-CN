---
title: ListPackage 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be09b76b-429b-4639-89f0-1eadb0c851ce
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65e90a4b28d89d4d30b2ca4c6c09977529db653a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65328664"
---
# <a name="listpackage-command"></a>ListPackage 命令
列出了生成的.msi 文件中包含的项目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="usage"></a>用法  
 **BTSTask ListPackage** [**/包：**<em>值</em>]  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|Description|  
|---------------|--------------|-----------------|  
|**/ 打包**或  **/P**|是|名称和路径的.msi 文件。 例如：C:\MSI\MyApplication.msi. 如果路径中包含空格，则必须放在双引号 （"） 中。|  
  
## <a name="sample"></a>示例  
 **ListPackage /Package:"C:\My MSI Files\MyApplication.msi"**  
  
## <a name="remarks"></a>备注  
 参数不区分大小写。 不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。  
  
## <a name="see-also"></a>请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)