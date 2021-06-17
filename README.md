 function sendEmbed($embed, $token) {
		$requestJson = json_encode(utf8ize($embed));
		$ch = curl_init();
		curl_setopt($ch, CURLOPT_URL, "https://api.zerotwo.bot/guild/chat/embed");
		curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
		curl_setopt($ch, CURLOPT_HTTPHEADER, array("X-ZeroTwo-Auth: ".$token));
		curl_setopt($ch, CURLOPT_POST, true);
		curl_setopt($ch, CURLOPT_POSTFIELDS, $requestJson);
		curl_exec($ch);
		curl_close($ch);
	}

    $embed = array(
		"channelId" => $channelId, // yes, dumb design, but the channel id is right here
		"title" => array(
			"text" => "EMBEDS FROM REST",
			"url" => "https://zerotwo.bot/"
		),
		"color" => $color,
		"description" => "you cum on",
		"fields" => array(
			array(
				"name" => "Name",
				"value" => "Value",
				"inline" => true
			),
			array(
				"name" => "Title",
				"value" => "Subtext",
				"inline" => true
			)
		),
		"thumbnail" => "https://media.giphy.com/media/CO7xyiUlvkG6Q/giphy.gif",
		"footer" => array(
			"text" => "NUT",
			"iconUrl" => "https://media.giphy.com/media/CO7xyiUlvkG6Q/giphy.gif"
		)
	);
