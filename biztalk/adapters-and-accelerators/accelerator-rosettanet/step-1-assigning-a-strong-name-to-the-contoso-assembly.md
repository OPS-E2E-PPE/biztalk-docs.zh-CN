---
title: 步骤 1： 为 Contoso 程序集分配强名称 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, assigning strong-names
- strong-named assemblies
ms.assetid: c8ec4593-5a4d-47ab-8799-7b2cd3d15ffc
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d388fc725b8aaeec4cbfa80c23bd5e2a1b42a27
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963859"
---
# <a name="step-1-assigning-a-strong-name-to-the-contoso-assembly"></a>步骤 1： 为 Contoso 程序集分配强名称
在此步骤中，你将为 BizTalk 程序集创建并分配一个强名称。 强名称通过分配一个数字签名和一个唯一的密钥对可确保程序集的唯一性。 此外，强名称还提供了完整性检查以确保自上次构建以来程序集的内容没有发生变化。  
  
### <a name="to-create-a-strong-name-assembly-key-file"></a>创建强名称程序集密钥文件  
  
1.  启动**Visual Studio 2012 的命令提示符**。  
  
2.  在命令提示符处，转到 Contoso 解决方案的位置。  
  
    > [!NOTE]
    >  默认情况下，Contoso 解决方案的位置是*\<驱动器\>*: \Documents and 设置\\*\<用户名\>* \MyDocuments\Visual Studio\<版本\>\Projects。  
  
3.  在命令提示符处，键入**sn-k FabConPriceAvail.snk**，然后按**Enter**。  
  
4.  在命令提示符处，键入**退出**，然后按**Enter**。  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a>指定程序集的强名称  
  
1.  在解决方案资源管理器，右键单击**ContosoPriceAndAvailability**项目，，然后单击**属性**。  
  
2.  在属性页中，单击**签名**的左窗格中。  
  
3.  在右窗格中，选择**对程序集签名**。  
  
4.  单击**浏览**在选择强名称密钥文件字段。  
  
5.  找到你的项目文件夹中，选择**FabConPriceAvail.snk**你之前，创建文件，然后单击**打开**。  
  
6.  单击**确定**以保存所做的更改。  
  
7.  在解决方案资源管理器，右键单击**ContosoPriceAndAvailability**项目，，然后单击**生成**。 已成功生成后，再次右键单击项目，然后单击**部署**。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 2： 为 Contoso 3A2 价格和可用性查询/响应方案创建端口](step-2-create-ports-for-contoso-3a2-price-and-availability-query.md)