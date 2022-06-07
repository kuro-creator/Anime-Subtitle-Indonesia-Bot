var token = ""; // token bot telegram
var SheetID = ""; // id google sheet

function doPost(e) {
  var stringJson = e.postData.getDataAsString();
  var updates = JSON.parse(stringJson);
 
    if(updates.message.text){
      sendText(updates.message.chat.id,searchAnimeById(updates.message.text)); 
    }
 
}
function getRows(){
  var rangeName = 'Anime List!A2:C'; 
  var rows = Sheets.Spreadsheets.Values.get(SheetID, rangeName).values;
  return rows;
}

function searchAnimeById(idanime){
  var dataanime = getRows();
  for (var row = 0; row < dataanime.length; row++) {
    if(dataanime[row][0]==idanime){ 
      return dataanime[row][1];
    }
  }
  return "Anime yang anda cari tidak ditemukan. Ketik perintah /filters untuk melihat anime yang sudah masuk dalam database bot.";
}
function testgetrow(){
  var nama = searchAnimeById(type=text);
  var x = "";
 
}
function sendText(chatid,text,replymarkup){
var data = {
    method: "post",
    payload: {
      method: "sendMessage",
      chat_id: String(chatid),
      text: text,
      parse_mode: "HTML",
      reply_markup: JSON.stringify(replymarkup)
    }
  };
  UrlFetchApp.fetch('https://api.telegram.org/bot' + token + '/', data);
}
