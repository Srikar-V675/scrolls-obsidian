```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "Decks/Accenture",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
