---
title: AS2 over File （BizTalk Server 示例） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fed2344-8181-4c85-a2ef-a421fc40dce1
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14d4c077cce861e94f6c2cdc0bfc6f4a14669340
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "25966787"
---
# <a name="as2-over-file-biztalk-server-sample"></a>AS2 over File （BizTalk Server 示例）
AS2 Over File 範例示範如何透過 FILE 接收位置接收 AS2 訊息。 這可讓您使用 FILE 配接器來接收 AS2 訊息，而不是通常使用的 HTTP 配接器。 若要這樣做，此解決方案會在 AS2 解碼器要求時，將 AS2 訊息中的 HTTP 標頭寫入 InboundHTTPHeaders 內容屬性。  
  
## <a name="what-this-sample-does"></a>此範例的用途  
 本範例示範如何在沒有 HTTP 配接器的情況下處理 AS2 訊息中的 HTTP 標頭。 具體來說，本範例執行下列工作：  
  
1.  當您將測試訊息拖曳到輸入資料夾時，FILE 接收位置會收取該訊息。  
  
2.  自訂 AS2 接收管線中的自訂管線元件會處理訊息，將其 HTTP 標頭寫入 InboundHTTPHeaders 內容屬性。  
  
    > [!NOTE]
    >  如果處理訊息導致自訂管線元件的下游失敗，您可能無法繼續處理訊息，因為它已經轉換成 XML 編碼。  
  
3.  自訂接收管線中的 AS2 解碼器會處理訊息，讀取 InboundHTTPHeaders 內容屬性中的屬性來執行其處理。  
  
4.  傳送埠會訂閱接收管線所產生的 XML 訊息，藉由通過傳送管線傳遞該訊息，然後再將它放入輸出資料夾中。  
  
## <a name="where-to-find-this-sample"></a>可在何處找到此範例  
 此示例位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装文件夹： [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 通过文件。  
  
 下表顯示此範例中的檔案，並描述其用途。  
  
|檔案|Description|  
|---------------|-----------------|  
|AS2OverFile.csproj|包含自訂管線元件程式碼的專案。|  
|AS2OverFile.sln|包含 AS2OverFile.btproj 專案的解決方案。|  
|Program.cs|包括表示标头数据的类。|  
|SampleMessage.txt|包含 HTTP 標頭的範例訊息。|  
  
## <a name="implementing-and-running-this-sample"></a>實作及執行此範例  
 若要實作 AS2 Over File 範例，您必須執行下列作業：  
  
-   建置及部署此範例的 BizTalk 專案，並建立自訂管線元件  
  
-   建立使用自訂管線元件的自訂管線，並使用該自訂管線建置及部署專案  
  
-   建立輸入及輸出檔案資料夾  
  
-   設定接收埠和位址，並啟用接收位置  
  
-   設定傳送埠及啟動傳送埠  
  
-   创建发送示例消息的参与方  
  
#### <a name="to-build-a-custom-pipeline-with-the-as2-over-file-emulator-pipeline-component"></a>若要使用 AS2 Over File 模擬器管線元件建置自訂管線  
  
1.  在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\Samples\AS2\AS2 Over File 文件夹中的 AS2OverFile 项目。  
  
2.  建立強式名稱金鑰檔，開啟 AS2OverFile 專案的 [屬性] 對話方塊，然後將金鑰檔指派給專案。  
  
3.  建置專案。  
  
4.  在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，创建名为 AS2OverFile_Pipeline 的新 BizTalk 项目。  
  
5.  右键单击 AS2OverFile_Pipeline 项目，指向 **添加**, ，然后单击 **新项**。  
  
6.  在 **添加新项** 对话框中，选择 **管道文件** 在左侧窗格中，选择 **接收管道** 在右侧窗格中，将管道 AS2OverFile_Receive.btp，，然后单击 **添加**。  
  
7.  单击 **视图** 在菜单栏上，然后单击 **工具箱** ，显示工具箱。  
  
8.  在工具箱中，右键单击 **BizTalk 管道组件**, ，然后单击 **选择项**。  
  
9. 在 **选择工具箱项** 对话框中，单击 **BizTalk 管道组件** 选项卡。单击**AS2 通过文件模拟器**，然后单击**确定**。  
  
10. 通过打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 命令提示符，并对 \AS2 Over File\obj\Debug 文件夹中的 Microsoft.BizTalk.Sdk.Components.AS2OverFile.dll 执行命令 `gacutil /if "<file name and path>"`，将 AS2OverFile.dll 文件添加到全局程序集缓存中。  
  
11. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，从到工具箱中拖动文件模拟器通过 AS2 管道组件**解码**自定义管道的阶段。  
  
12. 将组件拖到 AS2 解码器组件 **解码** 自定义管道之后 AS2 通过文件组件, 的阶段。  
  
    > [!NOTE]
    >  如果要產生 MDN，請將 AS2 解譯器新增到自訂管線的 [解譯] 階段中。 如果您不是要傳回 MDN，就不需要 AS2 解譯器。  
  
13. 建立強式名稱金鑰檔，開啟 AS2OverFile_Pipeline 專案的 [屬性] 對話方塊，然後將金鑰檔指派給專案。  
  
14. 建置和部署自訂管線。  
  
15. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，通过单击管道节点，然后单击向管道节点中添加自定义管道**刷新**。  
  
#### <a name="to-implement-the-solution-for-this-sample"></a>若要實作本範例的解決方案  
  
1.  在 Windows 资源管理器中的 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\SDK\Samples\AS2\AS2 Over File 文件夹中，创建一个 In 输入文件夹和一个 Out 输出文件夹。  
  
2.  在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，创建一个名为 AS2OverFile_Receive 的单向接收端口。 在接收埠中，使用下列屬性來建立接收位置：  
  
    |屬性|設定|  
    |--------------|-------------|  
    |名稱|AS2OverFile_Receive|  
    |型別|FILE|  
    |接收資料夾|[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File/In|  
    |檔案遮罩|*.txt|  
    |接收管線|AS2OverFile|  
  
3.  在接收位置节点中，右键单击 AS2OverFile_Receive 接收位置，然后单击 **启用**。  
  
4.  在 [傳送埠] 節點中，使用下列屬性建立靜態單向傳送埠：  
  
    |屬性|設定|  
    |--------------|-------------|  
    |名稱|AS2OverFile_Send|  
    |型別|FILE|  
    |接收資料夾|[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File/Out|  
    |檔案遮罩|%MessageID%.xml|  
    |傳送管線|Passthru|  
    |篩選|BTS.REceivePortName == AS2OverFile_Receive|  
  
5.  在发送端口节点中，右键单击 AS2OverFile_Send 发送端口，并依次 **启动**。  
  
6.  在 [合作對象] 節點中，建立名稱為 "Partner" 的合作對象。 将与别名添加到别名列表中， **名称** 的 **EDIINT AS2 从值**, 、 **限定符** 的 **AS2-从**, ，和一个 **值** 的 **合作伙伴**。  
  
 BizTalk Server 現在已準備就緒可使用此範例。  
  
## <a name="running-this-sample"></a>執行此範例  
 請使用下列程序執行 AS2 Over File 範例。  
  
#### <a name="to-run-this-sample"></a>執行此範例  
  
1.  将该 SampleMessage.txt 文件从 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File 文件夹复制到 \AS2 Over File\In 文件夹。  
  
2.  確認輸出 XML 訊息已放入 \AS2 Over File\Out 輸出資料夾。  
  
3.  在文本编辑器中，打开输入的消息 SampleMessage.txt 并打开输出消息\<GUID\>在文本编辑器中的.xml。 確認 SampleMessage.txt 輸入訊息有 HTTP (和 AS2) 標頭，而輸出訊息則沒有 HTTP 標頭。  
  
## <a name="classes-or-methods-used-in-this-sample"></a>在此範例中使用的類別或方法  
 無  
  
## <a name="see-also"></a>另請參閱  
 [EDI 和 AS2 （BizTalk Server 的示例文件夹）](../core/edi-and-as2-biztalk-server-samples-folder.md)   
 [通过 FILE 发送端口发送 AS2 消息](../core/sending-an-as2-message-over-a-file-send-port.md)