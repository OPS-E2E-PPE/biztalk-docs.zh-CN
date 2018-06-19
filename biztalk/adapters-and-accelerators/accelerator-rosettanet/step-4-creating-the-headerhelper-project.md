---
title: 步骤 4： 创建 HeaderHelper 项目 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects, helper projects
- private process tutorial, creating helper projects
ms.assetid: 82413537-032a-4368-8d77-d024a7c83b0b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2525e0e87106e2eeb82fb05b52b3ec69d4be876d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965523"
---
# <a name="step-4-creating-the-headerhelper-project"></a>步骤 4： 创建 HeaderHelper 项目
在此步骤中，将创建 [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] 类库。 当专用业务流程收到传入消息时，HeaderHelper 库确定是否需要进行文档转换，如果需要，则执行该转换。 这使你的业务流程能够使用不同版本的 RosettaNet 实现框架 (RNIF) 文档。 此外，当发出 3A2 响应消息时，HeaderHelper 库在传送该消息之前执行另一种文档转换。  
  
### <a name="to-create-the-headerhelper-project"></a>创建 HeaderHelper 项目  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器，右键单击 Contoso 解决方案，指向**添加**，然后单击**新项目**。  
  
2.  在项目类型窗格中，添加新项目对话框中选择**Visual C#**。  
  
3.  在模板窗格中，选择**类库**模板。  
  
4.  在**名称**框中，键入**HeaderHelper**，然后单击**确定**以创建该项目。  
  
5.  在解决方案资源管理器，右键单击**Class1.cs**文件中**HeaderHelper**项目中，单击**重命名**，类型**HeaderHelper.cs**，然后按**Enter**。  
  
### <a name="to-create-the-helper-class"></a>创建 Helper 类  
  
1.  在解决方案资源管理器，展开**HeaderHelper**项目，，然后双击**HeaderHelper.cs**节点，以打开 HeaderHelper 源文件。  
  
2.  在源文件中键入以下代码，覆盖全部现有代码：  
  
    ```  
    using System;  
    using System.Xml;  
  
    namespace ContosoPriceAndAvailability  
    {  
        public class Helper  
        {  
            static public XmlDocument NormalizeHeader( XmlDocument curPip )  
            {  
                string strInput = curPip.OuterXml;  
                try  
                {  
                    XmlDocument xDoc = new XmlDocument();  
  
                    strInput = strInput.Replace("<!DOCTYPE Pip3A2PriceAndAvailabilityQuery SYSTEM \"3A2PriceAndAvailabilityQueryMessageGuideline_v1_3.dtd\"[]>",String.Empty);  
                    strInput = strInput.Replace("<Pip3A2PriceAndAvailabilityQuery>","<Pip3A2PriceAndAvailabilityQuery xmlns=\"http://schemas.microsoft.com/biztalk/btarn/2004/3A2PriceAndAvailabilityQueryMessageGuideline_v1_3.dtd\">");  
                    strInput = strInput.Replace("xml:",String.Empty);  
                    strInput = strInput.Replace("b:",String.Empty);  
                    strInput = strInput.Replace("lang:",String.Empty);  
                    strInput = strInput.Replace("ns1:",String.Empty);  
  
                    xDoc.LoadXml(strInput);  
  
                    return xDoc;  
                }  
                catch(Exception ex)  
                {  
                    System.Diagnostics.Debug.Write( ex.Message );  
                    throw ex;  
                }  
            }  
  
            static public string ReturnSCWithDocType( XmlDocument xmlDoc )  
            {  
                try  
                {  
                    string sResponse = xmlDoc.InnerXml;  
                    sResponse=sResponse.Replace("ns0:",String.Empty);  
                    xmlDoc.LoadXml(sResponse);  
                    xmlDoc.DocumentElement.RemoveAllAttributes();  
                    sResponse = xmlDoc.InnerXml;  
  
                    sResponse = sResponse.Insert(0,"<!DOCTYPE Pip3A2PriceAndAvailabilityResponse SYSTEM \"3A2PriceAndAvailabilityResponseMessageGuideline_v1_3.dtd\">");  
                    sResponse = sResponse.Replace("ns0:",String.Empty);  
                    sResponse = sResponse.Replace("b:",String.Empty);  
                    sResponse = sResponse.Replace("lang:",String.Empty);  
                    sResponse = sResponse.Replace("ns1:",String.Empty);  
  
                    return sResponse;  
                }  
                catch(Exception ex)  
                {  
                    throw ex;  
                }  
            }  
        }  
    }  
    ```  
  
3.  在“文件”  菜单上，单击“全部保存” 。  
  
### <a name="to-create-a-strong-named-assembly-for-the-headerhelper-project"></a>为 HeaderHelper 项目创建强名称程序集  
  
1.  在解决方案资源管理器，右键单击**HeaderHelper**项目，，然后单击**属性**。  
  
2.  在 HeaderHelper 属性页对话框中，选择**签名**HeaderHelp 属性窗格中的左窗格中。  
  
3.  在右窗格中，单击**对程序集签名**。  
  
4.  单击**选择强名称密钥文件**文本框中，然后选择**\<浏览\>** 从下拉列表。  
  
5.  在选择文件对话框中，移动到的位置您 Contoso 的程序集，并双击**FabConPriceAvail.snk**。  
  
6.  在“文件”  菜单上，单击“全部保存” 。  
  
7.  在解决方案资源管理器，展开**HeaderHelper**项目中，展开**属性**节点，然后再双击**AssemblyInfo.cs**节点，以打开 AssemblyInfo.cs源文件。  
  
8.  在 AssemblyInfo.cs 源文件的 AssemblyCulture 属性后面的行中，键入以下代码：  
  
    ```  
    [assembly: AssemblyKeyFile("../../../FabConPriceAvail.snk")]  
    ```  
  
9. 在“文件”  菜单上，单击“全部保存” 。  
  
### <a name="to-build-and-deploy-the-headerhelper-project"></a>生成和部署 HeaderHelper 项目  
  
1.  在解决方案资源管理器，右键单击**HeaderHelper**项目，，然后单击**生成**。  
  
2.  启动**Visual Studio 2012 的命令提示符**。  
  
3.  在命令提示符下，将移动到的位置**HeaderHelper**项目输出目录 （的 \Bin\Debug 文件夹中）。  
  
4.  在命令提示符处，键入**gacutil /if HeaderHelper.dll**按**Enter**安装**HeaderHelper**到的程序集**全局程序集缓存**.  
  
## <a name="see-also"></a>另请参阅  
 [步骤 5：修改 Contoso 私有业务流程](../../adapters-and-accelerators/accelerator-rosettanet/step-5-modifying-the-contoso-private-process-orchestration.md)