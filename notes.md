⏺ moderncv styles (already installed — just change \moderncvstyle{...}):                                
                                                                                                        
  ┌──────────┬───────────────────────────────────────────────────────────────────┐                      
  │  Style   │                            Description                            │
  ├──────────┼───────────────────────────────────────────────────────────────────┤                      
  │ classic  │ Current — name left, contact right, colored left column for dates │                    
  ├──────────┼───────────────────────────────────────────────────────────────────┤                      
  │ banking  │ No icons, bold section rules, more compact                        │                      
  ├──────────┼───────────────────────────────────────────────────────────────────┤                      
  │ casual   │ Name large top-left, photo circle, relaxed spacing                │                      
  ├──────────┼───────────────────────────────────────────────────────────────────┤                      
  │ fancy    │ Colored header band across the top                                │
  ├──────────┼───────────────────────────────────────────────────────────────────┤                      
  │ oldstyle │ Traditional serif look, minimal decoration                        │
  └──────────┴───────────────────────────────────────────────────────────────────┘                      
                                                            
  Each works with color options: blue, orange, green, red, purple, grey, black                          
   
  ---                                                                                                   
  Other popular LaTeX CV packages (may need installing):    
                                                                                                        
  ┌─────────────────┬───────────────────────────────────────────────────────┐
  │     Package     │                         Style                         │                           
  ├─────────────────┼───────────────────────────────────────────────────────┤
  │ altacv          │ Two-column, sidebar layout — very modern              │
  ├─────────────────┼───────────────────────────────────────────────────────┤
  │ awesome-cv      │ Sleek, colored header, icon-heavy — popular on GitHub │                           
  ├─────────────────┼───────────────────────────────────────────────────────┤                           
  │ europecv        │ EU Europass standard format                           │                           
  ├─────────────────┼───────────────────────────────────────────────────────┤                           
  │ twentysecondscv │ Two-column with sidebar timeline                      │
  ├─────────────────┼───────────────────────────────────────────────────────┤                           
  │ curve           │ Modular, section-based                                │
  └─────────────────┴───────────────────────────────────────────────────────┘                           
                                                            
  ---
  The quickest way to experiment is to stay within moderncv — just swap the style and color:
                                                                                                        
  \moderncvstyle{banking}   % or casual, fancy, oldstyle
  \moderncvcolor{orange}    % or green, red, purple, grey, black                                        
                                                            
  Want me to switch to any of these?        

                                                            
⏺ Here's a full breakdown of moderncv options:                                                          
                                                                                                      
  Styles (\moderncvstyle{...})                                                                          
  classic    % date column left, content right — traditional academic look                              
  banking    % no icons, rules under sections, compact — currently active                               
  casual     % large name top-left, optional photo, relaxed                                             
  fancy      % colored header band across full width                                                    
  oldstyle   % serif fonts, bullet separators, minimal decoration                                       
                                                                                                        
  Colors (\moderncvcolor{...})                                                                          
  blue       % currently active                                                                         
  orange                       
  green                                                                                                 
  red                                                                                                 
  purple
  grey  
  black
       
  Font size (document class option)
  \documentclass[10pt, a4paper]{moderncv}   % smaller                                                   
  \documentclass[11pt, a4paper]{moderncv}   % current
  \documentclass[12pt, a4paper]{moderncv}   % larger                                                    
                                                                                                      
  Paper size (document class option)                                                                    
  a4paper    % current                                                                                  
  letterpaper         
                                                                                                        
  Photo (optional, works well with casual)                                                            
  \photo[64pt][0.4pt]{photo.jpg}   % [size][border thickness]{file}                                     
  
  Name font (override default)                                                                          
  \renewcommand{\namefont}{\Huge\bfseries}                                                            
                                                                                                        
  Hint column width (the left date/label column)                                                        
  \setlength{\hintscolumnwidth}{3cm}   % default is ~3cm                                                
                                                                                                        
  Quote (tagline under name, works in casual/classic)                                                   
  \quote{PhD Researcher in Bioinformatics \& Computational Biology}                                     
                                                                                                             


⏺ \cventry takes 6 arguments:

  \cventry{date}{title}{institution}{location}{grade}{description}

  Example from your CV:
  \cventry{2022--Present}{PhD Research Scholar}{University of North Bengal}{Siliguri, India}{}{}


  ┌───────────────┬────────────────────────────────┐
  │   Argument    │        What it renders         │
  ├───────────────┼────────────────────────────────┤
  │ {date}        │ Left column (the hint/date)    │
  ├───────────────┼────────────────────────────────┤
  │ {title}       │ Bold text                      │
  ├───────────────┼────────────────────────────────┤
  │ {institution} │ Italic text after title        │
  ├───────────────┼────────────────────────────────┤
  │ {location}    │ Italic, after institution      │
  ├───────────────┼────────────────────────────────┤
  │ {grade}       │ After location, in parentheses │
  ├───────────────┼────────────────────────────────┤
  │ {description} │ Below the entry, indented      │
  └───────────────┴────────────────────────────────┘

  Leave any field empty with {} — it simply won't render.

  The description field is where you put bullet points:
  \cventry{2022--Present}{PhD Research Scholar}{University of North Bengal}{Siliguri, India}{}{
    \begin{itemize}
      \item First point
      \item Second point
    \end{itemize}
  }

  In your CV, the description is currently passed as a separate block after the \cventry — which
   also works since moderncv doesn't add extra spacing either way.