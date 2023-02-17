# chatGPT3-notes
Some notes about coding chatGPT3

**a string to input in chatGPT make sense, ex:**

```
prompt = 'College funding solutions';
$style_text = 'research';
$tone_text = 'Writing tone: cheerful';
$prompt  .= '. ' . $style_text . ', ' . $tone_text . '.';
```

**echo the prompt:**

```
College funding solutions. research, Writing tone: cheerful.
```

**with style and tone can get from 2 functions below**

```

if (! function_exists('writing_style')) {
    function writing_style($style) {
        $styles = [
            "descr" => "descriptive",
            "creat" => "creative",
            "narra" => "narrative",
            "persu" => "persuasive",
            "expos" => "expository",
            "infor" => "informative",
            "refle" => "reflective",
            "argum" => "argumentative",
            "analy" => "analytical",
            "criti" => "critical",
            "evalu" => "evaluative",
            "journ" => "journalistic",
            "techn" => "technical",
            "repor" => "report",
            "resea" => "research",
            "simpl" => "simple",
            "compa" => "comparative",
            "detai" => "detailed",
            "conci" => "concise",
            "artic" => "articulate",
            "acade" => "academic",
            "busin" => "business",
            "casua" => "casual",
            "collo" => "colloquial",
            "ficti" => "fiction",
            "poeti" => "poetic",
            "drama" => "dramatic",
            "perso" => "personal",
            "biogr" => "biographical",
            "lyric" => "lyrical",
            "dialo" => "dialogue",
            "monol" => "monologue",
            "blog" => "blog",
            "lette" => "letter",
            "satir" => "satirical",
            "pasto" => "pastoral",
            "histo" => "historical",
            "news" => "news",
            "anect" => "anecdotal",
            "senso" => "sensory",
            "vivid" => "vivid"
        ];
        return !empty($styles[$style]) ? $styles[$style] : '';
    }
}

if (! function_exists('writing_tone')) {
    function writing_tone($tone) {
        $tones = [
            "formal" => "Writing tone: formal",
            "asser" => "Writing tone: assertive",
            "cheer" => "Writing tone: cheerful",
            "humor" => "Writing tone: humorous",
            "inspi" => "Writing tone: inspirational",
            "sarca" => "Writing tone: sarcastic",
            "informal" => "Writing tone: informal",
            "neutr" => "Writing tone: neutral",
            "skept" => "Writing tone: skeptical",
            "optim" => "Writing tone: optimistic",
            "worry" => "Writing tone: worried",
            "curio" => "Writing tone: curious",
            "surpr" => "Writing tone: surprised",
            "encou" => "Writing tone: encouraging",
            "disap" => "Writing tone: disappointed",
            "profe" => "Writing tone: professional",
            "conve" => "Writing tone: conversational",
            "polite" => "Writing tone: polite",
            "sensit" => "Writing tone: sensitive",
            "sincere" => "Writing tone: sincere",
            "friendly" => "Writing tone: friendly",
            "scien" => "Writing tone: scientific",
            "factual" => "Writing tone: factual"
        ];

        return !empty($tones[$tone]) ? $tones[$tone] : '';
    }
}

```


# seperate content of chatGPT3 in PHP

```
$text = '';// content from response of chatGPT3
$complete = trim($text);
$str = preg_replace('/\n$/', '', preg_replace('/^\n/', '', preg_replace('/[\r\n]+/', "\n", $text)));
$options = preg_split("/\r\n|\n|\r/", $str);
// delete 1. 2. 3. etc from beginning of the line
$options = preg_replace('/^\\d+\\.\\s/', '', $options);
// delete if there is a dot at the end of the line
$options = preg_replace('/\\.$/', '', $options);
```

