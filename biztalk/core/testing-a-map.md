---
title: 测试映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 265afd62-3c1d-4b9a-9f51-176b9b079241
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a40963bffc97fa2b1057331a3adda3e846b039e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299298"
---
# <a name="testing-a-map"></a>测试映射
在设计时，可以在 EDI 项目中测试映射。 若要执行此操作，您使用的 XML 工具扩展[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境。 本主题介绍如何设置和使用**测试映射**XML 工具扩展的功能。  
  
 通过指定一个源文档，并指定一个文件夹中测试映射其中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将保存生成的实例 （具有虚构数据）。 您需要设置分隔符的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将用于处理源文档，并生成目标文档根据 EDI 架构。 这适用于的所有值**测试映射**输入映射的属性页中的属性：**生成实例**， **XML**，或**本机**。 它适用于**生成实例**因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]需要知道哪种分隔符生成实例使用。 它适用于**XML**或**本机**因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]需要知道如何解释本机平面文件或 XML 文件。 此外需要设置分隔符的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成输出文件时将使用。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="to-test-a-map"></a>若要测试映射  
  
1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，并添加你想要测试到项目，该映射将该映射的源和目标架构添加到项目。  
  
   > [!NOTE]
   >  无需生成项目以测试映射。  
  
2. 右键单击地图，然后单击**属性**。  
  
3. 在中**属性**窗口中，将**验证测试映射输入**到**True**如果想要验证根据源架构对输入的文件。 设置**验证测试映射输出**到**True**如果想要验证根据目标架构的输出文件。  
  
   > [!NOTE]
   >  如果测试具有的地图**测试映射输入**属性设置为**本机**并**验证测试映射输入**并**验证测试映射输出**属性设置为**False**，仍会执行验证。 这是因为本机格式输入的文件将转换为 XML 格式和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将验证针对该架构的 XML。 如果输入实例中有验证问题，请验证机制将即使发布错误，**验证测试映射输入**并**验证测试映射输出**属性设置为**False**。  
  
4. 设置**测试映射输入**到**本机**对于具有.edi 扩展名的输入文件。 将其设置为**XML**如果它具有.xml 扩展名。 设置**测试映射输入**到**生成实例**具有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成输入的实例，而不是无需手动指定输入的实例。  
  
5. 设置**测试映射输出**到**本机**对于具有.edi 扩展名的输出文件。 将其设置为**XML**如果它具有.xml 扩展名。  
  
6. 有关**测试映射输入实例**，浏览到你想要用于测试映射，请选择它，输入实例，然后**打开**。 如果你想要将此属性留空，设置**测试映射输入**到**生成实例**。  
  
   > [!NOTE]
   >  您必须或者指定的输入的实例**测试映射输入实例**，或者设置**测试映射输入**到**生成实例**。 如果没有，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将生成错误。  
  
7. 有关**测试映射输出实例**，浏览到想要保存输出实例中的，为输出实例中，输入一个名称，然后单击的位置**保存**。  
  
   > [!NOTE]
   >  如果未指定输出实例，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将创建一个输出文件、 将输出文件放置到的文件夹，并指明文件名和路径。  
  
8. 右键单击您要测试，然后单击该地图**测试映射**。  
  
9. 在 X12 **EDI 实例属性**对话框框中，请确保所有属性都是与输入和输出实例的设置一致。  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将显示**EDI 实例属性**对话框中，在测试映射过程中两次： 一次用于解释输入的消息实例，一次针对生成输出消息实例。 但是，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可能多次显示该对话框并且可能会显示针对非 EDI 架构对话框。 如果是这样，请单击**确定**以关闭对话框。  
  
10. 单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [通过使用设计时 XML 工具](../core/using-design-time-xml-tools.md)