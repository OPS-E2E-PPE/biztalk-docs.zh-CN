---
title: UninstallApp 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f45c9530-8138-40f1-b279-1428c5a7fbbc
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4fc9da4d645b710490447addc2d4fd8691f199d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292683"
---
# <a name="uninstallapp-command"></a>UninstallApp 命令
从本地计算机中卸载 BizTalk 应用程序，并从列表中的程序中添加或删除程序控制面板中移除应用程序。 此命令的效果删除应用程序通过添加或删除程序。 如果为此应用程序安装了多个.msi 文件，将卸载的所有安装的.msi 文件的所有项。  
  
 添加或删除程序中所示，此命令指定的应用程序名称必须与应用程序的名称匹配。 如果您不确定的应用程序名称，则可以使用**ListPackage**命令来获取它，如中所述[ListPackage 命令](../core/listpackage-command.md)。  
  
> [!IMPORTANT]
>  尽管可以通过双击.msi 文件卸载的应用程序，但不支持执行此操作。 这是因为可以为同一应用程序，安装多个.msi 文件并使用此方法将不会卸载所有应用程序与关联的项。  
  
## <a name="usage"></a>用法  
 **BTSTask UninstallApp /ApplicationName:** *值*  
  
## <a name="parameters"></a>Parameters  
  
|参数|Required|Description|  
|---------------|--------------|-----------------|  
|**/ ApplicationName** (或 **/A**，请参阅备注)|是|若要卸载的 BizTalk 应用程序的名称。 如果名称包含空格，则必须将其括在双引号 （"）。|  
  
## <a name="sample"></a>示例  
 **BTSTask UninstallApp /ApplicationName:MyApplication**  
  
## <a name="remarks"></a>备注  
 参数不区分大小写。 不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。  
  
## <a name="see-also"></a>请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)   
 [如何卸载 BizTalk 应用程序](../core/how-to-uninstall-a-biztalk-application.md)